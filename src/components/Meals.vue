<template>
<div v-if="error">{{error}}</div>
<div>{{meals}}</div>
</template>

<script lang="ts">
import { defineComponent, onMounted, ref } from 'vue';

export default defineComponent({
  name: 'Meals',
  components: {
  },
  setup () {
    const meals = ref(null)
    const error = ref(false) 

    function fetchRecipes() {
        fetch('https://www.themealdb.com/api/json/v1/1/filter.php?c=Vegetarian')
        .then((response) => response.json())
        .then((data) => meals.value = data)
        .catch(() => error.value = true)
    }
    
    onMounted(() => {
      fetchRecipes()
    })

    return {meals, error, fetchRecipes}
  },
// data () {
// return {
//     meals: null,
//     error: null,
// }
// },
// methods: {
//     async fetchRecipes() {
//         fetch('https://www.themealdb.com/api/json/v1/1/filter.php?c=Vegetarian')
//         .then((response) => response.json())
//         .then((data) => this.meals = data)
//         .catch((error) => this.error = error)
//     }
// },
// mounted () {
//  this.fetchRecipes()
// }
});
</script>

<style>
</style>