<template>
  <div class="github">
    <a href="https://github.com/VulpesCodes/RenderView">Github</a>
  </div>
</template>
<script>
export default {
  name: "",
  data: () => ({

  })
}
</script>
<style scoped>
.github {
  padding: 10px;
  width: 100%;
  text-align: center;
  background-color: #363636;
  position: sticky;
  bottom: 0;
  color: #0094bd;
}
.github a{
  color: #0094bd;
  text-decoration: none;
}

.github :active{
  color: white;
  text-decoration: none;
}
</style>
