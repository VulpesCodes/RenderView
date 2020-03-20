<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form onsubmit="event.preventDefault();" class="pure-form">
        <input v-model="searchText" />
      </form>
    </div>
  </div>
  <ModelList :models="models" />

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
      return this.$root.$data.models.filter(model => model.name.toLowerCase().search(this.searchText) >= 0);
    }
  },
}

</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
  background-color: white;
}

form {
  display: table;
  width: 97%;
  margin-left: 2%;
  outline: none;
}


input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
  outline: none;
}
</style>
