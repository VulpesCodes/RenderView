<template>
<div id="app">
  <div id="menu">
    <div id="leftside">
      <router-link to="/signin">
        <button type="button" name="button" v-if="this.$root.$data.user===''">Sign In</button>
      </router-link>
      <div id="Hello-user" v-if="this.$root.$data.user!=''">
        Hello, {{this.$root.$data.user}}
      </div>
    </div>
    <div id="brand">
      <router-link to="/">
        <div id="brand-color">
          RENDERVIEW
        </div>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/">
        <div class="menu-item browse">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/favorites">
        <div class="menu-item">
          <p>Favorites</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>



<style>
* {
  box-sizing: border-box;
}
body {
  background-color: #1a1a1a;
    @import url("https://use.typekit.net/trr3fba.css");
    font-family: mr-eaves-xl-modern, sans-serif;
    font-weight: 700;

}
#menu {
  display: flex;
  justify-content: space-between;
  margin: 0 0 60px 0;
  padding:  10px 50px;
  background-color: #363636;
  align-text: center;
  font-size: 22px;
}
#menu a {
  color: #0094bd;
  text-decoration: none;
}
#menu a :active{
  color: white;
  text-decoration: none;
}
#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
  flex: 1;
  color: white;
  align-text: center;
}
#brand-color {
    color: white;
    font-weight: 700;
    font-size: 26px;
}
#side {
  flex: 1;
  grid-area: side;
  display: flex;
  justify-content: flex-end;
  align-text: center;
}
#side img {
  width: 50px;
}
#leftside {
  flex: 1;
  align-text: center;
  color: black;
}
#leftside button{
  background-color: #0094bd;
  border: none;
  height: 100%;
  color: white;
  font-weight: 700;
  font-size: 22px;
  border-color: #0094bd;
  border-radius: 5px;
  outline: none;
}
#leftside :active button{
  background-color: white;
  border: none;
  height: 100%;
  color: black;
  font-weight: 700;
  font-size: 22px;
  border-color: white;
  border-radius: 5px;
  outline: none;
}
#Hello-user{
  padding: 2px;
}
.menu-item {
  display: flex;
  flex-direction: column;
}
.menu-item p {
  margin: 0px;
}
.browse {
  margin-right: 50px;
}
</style>
