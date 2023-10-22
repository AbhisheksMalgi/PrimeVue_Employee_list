<template>
  <h1>Add</h1>
  <div class="container">
    <div class="row">
      <div class="grid">
        <div><input class="p-inputtext p-component" type="text" placeholder="Firstname"></div>
        <div><input class="p-inputtext p-component" type="text" placeholder="Lastname"></div>
        <div><input class="p-inputtext p-component" type="text" placeholder="Field of employment"></div>
        <div><input class="p-inputtext p-component" type="text" placeholder="Skills"></div>
        <button class="p-button p-component p-button-icon-only p-button-rounded" type="button"><span
            class="p-button-icon pi pi-plus"></span></button>
        <div><input class="p-inputtext p-component" type="text" placeholder="About"></div>
      </div>
      <button class="p-button p-component p-button-rounded" type="button"><span
          class="p-button-label">Cancel</span></button>
      <button class="p-button p-component p-button-rounded" type="button"><span
          class="p-button-label">Save</span></button>
    </div>
  </div>
</template>

<script setup>
import Button from 'primevue/button';
import { ref } from 'vue';

const text = ref();
</script>



<style scoped>
.container {
  display: flex;
  min-height: 100vh;
}

.p-button.p-button-icon-only {
  width: 3rem;
  padding: 0.75rem 0;
}

.p-button-rounded {
  margin-left: 0.75rem;
}

.p-component * {
  box-sizing: border-box;
}

.p-inputtext {
  margin: 0.75rem;
  width: 110%;
  font-family: Lato, Helvetica, sans-serif;
  font-size: 1rem;
  color: #033d78;
  background: #fff;
  padding: 0.75rem 0.75rem;
  border: 1px solid #2c5b8a;
  transition: background-color .2s, color .2s, border-color .2s, box-shadow .2s;
  appearance: none;
  border-radius: 6px;
}

h1 {
  margin: 1rem 0 1rem 0;
  font-family: inherit;
  font-weight: 600;
  line-height: 1.2;
  display: flex;
  align-items: center;
  justify-content: center;
  color: inherit;
}
</style>
