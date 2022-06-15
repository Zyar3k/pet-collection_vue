<template>
  <!-- <div class="home"></div> -->
  <AddPet @add-pet="addPet" />
  <Pets @remove-pet="removePet" @add-favorite="addFavorite" :pets="pets" />
</template>

<script>
// @ is an alias to /src
import Pets from "../components/Pets.vue";
import AddPet from "../components/AddPet.vue";
export default {
  name: "Home",
  components: { Pets, AddPet },
  methods: {
    // removePet(id) {
    //   if (confirm("Are you sure you want to remove this pet?")) {
    //     this.pets = this.pets.filter((pet) => pet.id !== id);
    //   }
    // },
    async removePet(id) {
      if (confirm("Are you sure you want to remove this pet?")) {
        const res = await fetch(
          `https://62a9e4e63b314385543dbec3.mockapi.io/pets/${id}`,
          {
            method: "DELETE",
          }
        );

        res.status === 200
          ? (this.pets = this.pets.filter((pet) => pet.id !== id))
          : alert("Delete failed!!");
      }
    },
    // addFavorite(id) {
    //   this.pets = this.pets.map((pet) =>
    //     pet.id === id ? { ...pet, isFavorite: !pet.isFavorite } : pet
    //   );
    // },
    async addFavorite(id) {
      const addFavorite = await this.fetchPet(id);
      const updatedFavorite = {
        ...addFavorite,
        isFavorite: !addFavorite.isFavorite,
      };

      const res = await fetch(
        `https://62a9e4e63b314385543dbec3.mockapi.io/pets/${id}`,
        {
          method: "PUT",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify(updatedFavorite),
        }
      );

      const data = await res.json();

      this.pets = this.pets.map((pet) =>
        pet.id === id ? { ...pet, isFavorite: data.isFavorite } : pet
      );
    },
    // addPet(pet) {
    //   this.pets = [...this.pets, pet];
    // },
    async addPet(pet) {
      const res = await fetch(
        "https://62a9e4e63b314385543dbec3.mockapi.io/pets",
        {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify(pet),
        }
      );
      const newPet = await res.json();
      this.pets = [...this.pets, newPet];
    },
    async fetchPets() {
      const res = await fetch(
        "https://62a9e4e63b314385543dbec3.mockapi.io/pets"
      );
      const data = await res.json();
      return data;
    },
    async fetchPet(id) {
      const res = await fetch(
        `https://62a9e4e63b314385543dbec3.mockapi.io/pets/${id}`
      );
      const data = await res.json();
      return data;
    },
  },
  data() {
    return {
      pets: [],
    };
  },
  async created() {
    this.pets = await this.fetchPets();
    // this.pets = [
    //   {
    //     id: 1,
    //     name: "Fido",
    //     age: 3,
    //     img: "https://images.dog.ceo/breeds/spaniel-brittany/n02101388_5179.jpg",
    //     isFavorite: true,
    //   },
    //   {
    //     id: 2,
    //     name: "Ruby",
    //     age: 4,
    //     img: "https://images.dog.ceo/breeds/spaniel-blenheim/n02086646_3484.jpg",
    //     isFavorite: false,
    //   },
    //   {
    //     id: 3,
    //     name: "Coco",
    //     age: 5,
    //     img: "https://images.dog.ceo/breeds/terrier-tibetan/n02097474_8589.jpg",
    //     isFavorite: false,
    //   },
    // ];
  },
};
</script>
