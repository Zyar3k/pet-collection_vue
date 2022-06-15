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
    removePet(id) {
      if (confirm("Are you sure you want to remove this pet?")) {
        this.pets = this.pets.filter((pet) => pet.id !== id);
      }
    },
    addFavorite(id) {
      this.pets = this.pets.map((pet) =>
        pet.id === id ? { ...pet, isFavorite: !pet.isFavorite } : pet
      );
    },
    addPet(pet) {
      this.pets = [...this.pets, pet];
    },
  },
  data() {
    return {
      pets: [],
    };
  },
  created() {
    this.pets = [
      {
        id: 1,
        name: "Fido",
        age: 3,
        img: "https://images.dog.ceo/breeds/spaniel-brittany/n02101388_5179.jpg",
        isFavorite: true,
      },
      {
        id: 2,
        name: "Ruby",
        age: 4,
        img: "https://images.dog.ceo/breeds/spaniel-blenheim/n02086646_3484.jpg",
        isFavorite: false,
      },
      {
        id: 3,
        name: "Coco",
        age: 5,
        img: "https://images.dog.ceo/breeds/terrier-tibetan/n02097474_8589.jpg",
        isFavorite: false,
      },
    ];
  },
};
</script>
