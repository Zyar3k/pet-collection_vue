<template>
  <div style="margin-top: 20px">
    <div class="formgroup-inline">
      <div class="field">
        <label for="name" class="p-sr-only">name</label>
        <input
          id="name"
          type="text"
          class="text-base text-color surface-overlay p-2 border-1 border-solid surface-border border-round appearance-none outline-none focus:border-primary"
          placeholder="Name"
        />
      </div>
      <div class="field">
        <label for="age" class="p-sr-only">Age</label>
        <input
          id="age"
          type="number"
          class="text-base text-color surface-overlay p-2 border-1 border-solid surface-border border-round appearance-none outline-none focus:border-primary"
          placeholder="Age"
        />
      </div>
      <div class="field">
        <label for="url" class="p-sr-only">URL</label>
        <input
          id="url"
          type="text"
          class="text-base text-color surface-overlay p-2 border-1 border-solid surface-border border-round appearance-none outline-none focus:border-primary"
          placeholder="Image URL"
        />
      </div>
      <button
        type="button"
        class="text-white bg-primary-500 border-primary-500 px-3 py-2 text-base border-1 border-solid border-round cursor-pointer transition-all transition-duration-200 hover:bg-primary-600 hover:border-primary-600 active:bg-primary-700 active:border-primary-700"
      >
        Save
      </button>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
