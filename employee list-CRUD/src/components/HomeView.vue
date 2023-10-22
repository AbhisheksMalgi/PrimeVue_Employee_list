<template>
  <header>
    <h1>{{ title }}</h1>
    <Button @btn-click="$emit('toggle-add')" :text="showAdd ? 'close' : 'Add'" :color="lilac" />
  </header>
</template>


<script>
import Button from './Button.vue';

export default {
  name: 'Homeview',
  props: {
    title: 'string',
    showAdd: Boolean
  },
  components: {
    Button,
  }
}
</script>
  
  
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>