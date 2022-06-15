<template>
  <div class="pets">
    <div v-for="pet in pets" :key="pet.id">
     
      <Pet :pet="pet" />
    </div>
  </div>
</template>

<script>
import Pet from "./Pet.vue";
export default {
  //   props: ["pets"],
  props: {
    pets: Array,
  },
  components: {
    Pet,
  },
};
</script>

<style></style>
