<template>
  <div class="pet">
    <!-- <h3>{{ pet.name }}</h3> -->
    <Card>
      <template #header>
        <img src="{{ pet.img }}" />
      </template>
      <template #title>{{ pet.name }}</template>
      <template #subtitle>Age: {{ pet.age }}</template>
      <!-- <template #content>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore
          sed consequuntur error repudiandae numquam deserunt quisquam repellat
          libero asperiores earum nam nobis, culpa ratione quam perferendis
          esse, cupiditate neque quas!
        </p>
      </template> -->
      <template #footer>
        <Button
          icon="pi pi-times"
          label="Remove"
          class="p-button-danger"
          style="margin-right: 4em"
        />
        <Button icon="pi pi-heart" class="p-button-rounded p-button-danger" />
        <Button
          icon="pi pi-heart"
          class="p-button-rounded p-button-danger p-button-outlined"
        />
      </template>
    </Card>
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
