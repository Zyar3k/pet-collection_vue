<template>
  <div class="pet">
    <h3>{{ pet.name }}</h3>
    <div class="pet-image">
      <img :src="pet.img" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    pet: Object,
  },
};
</script>

<style></style>
