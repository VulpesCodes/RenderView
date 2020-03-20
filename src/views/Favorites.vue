<template>
<div>
  <ModelList :models="models" />
  <div class="no-Favorites" v-if="models.length===0">
    <h1>Empty</h1>
    <h3>It appears you don't have any favorites yet
    <br> Click on the stars to save them here</h3>
  </div>
</div>
</template>


<script>
import ModelList from "../components/ModelList.vue"
export default {
  name: 'Home',
  components: {
    ModelList
  },
  data() {
  return {
    searchText: '',
  }
  },
  computed: {
    models() {
      return this.$root.$data.models.filter(model => model.fave === true);
    }
  },
}

</script>


<style scoped>

.no-Favorites {
  color: white;
  width: 60%;
  background-color: #363636;
  margin: auto;
  text-align: center;
  padding: 100px;
}


</style>
