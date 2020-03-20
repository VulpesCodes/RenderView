<template>
  <div class="wrapper">
    <div class="models">
      <div class="model" v-for="model in models" :key="model.id">
        <div class="infobar">
          <div class="infotext">
            <h1>{{model.name}}</h1>
            <p>{{model.author}}</p>
          </div>
          <div class="favebutton">
            <button class="auto" v-on:click="model.fave = addFave(model.fave)">
              <img v-if="model.fave===false" id="star" src='../assets/empty-star.png'>
              <img v-if="model.fave===true" id="star" src='../assets/star.png'>
            </button>
          </div>
        </div>
        <div class="image">
          <iframe title="A 3D model" width="500" height="300" :src=model.image frameborder="0" allow="autoplay; fullscreen; vr" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
        </div>
        <div class="infobar">
          <p>Category: {{model.category}}</p>
        </div>
      </div>
    </div>
  </div>
</template>



<script>
  export default {
      name: 'ModelList',
        props: {
          models: Array
          },
      methods: {
        addFave(item) {
          if (item===false) {
            item = true;
          }
          else if (item===true) {
            item = false;
          };
          return item;
          }
        }
      }
</script>


<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.models {
  margin-top: 20px;
  margin-left: 10%;
  margin-right: 10%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.model {
  margin: 10px;
  margin-top: 50px;
  width: 500px;
  overflow: hidden;
}

.model img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.model .image {
  display: flex;
  justify-content: center;
}

.infobar {
  display: flex;
  background: #0094bd;
  color: #000;
  padding: 10px 30px;
  height: auto;
  justify-content: space-between;
}

.infobar h1 {
  font-size: 20px;
}

.infobar h2 {
  font-size: 16px;
}

.infobar p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
}

button {
  height: 60px;
  background: #000;
  color: white;
  border: none;
  display: inline-block;
  margin-top: auto;
  margin-bottom: auto;
}
#star {
  margin-top: 5px;
  width: 50px;
  height: 50px;
  border: none;
}

.auto {
  margin-left: 20%;
  margin-top: auto;
  margin-bottom: auto;
}
</style>
