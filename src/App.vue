<template>
<Meals />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Meals from './components/Meals.vue'

export default defineComponent({
  name: 'App',
  components: {
    Meals
  },
});
</script>

<style>
</style>
