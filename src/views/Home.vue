<template>
  <div class="home"></div>
  <Pets :pets="pets" />
</template>

<script>
// @ is an alias to /src
import Pets from "../components/Pets.vue";
export default {
  name: "Home",
  components: { Pets },
  data() {
    return {
      pets: [
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
      ],
    };
  },
};
</script>
