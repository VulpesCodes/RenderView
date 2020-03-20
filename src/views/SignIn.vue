<template>
<div>
  <div class="wrapper">
    <div id="SignInBox">
      <h1>Sign In</h1> <br>
      <hr>
      <br>
      <div id="interface">
        <h2>Username:</h2>
      <div class="search">
        <form v-on:submit.prevent="userSubmit" class="pure-form">
          <input v-model="usernameText" />
        </form>
      </div>
      <h2>Password:</h2>
      <div class="search">
        <form v-on:submit.prevent="userSubmit" class="pure-form">
          <input v-model="passwordText" />
        </form>
      </div>
      <br>
      <br>
    </div>
    </div>
  </div>
</div>
</template>


<script>
export default {
  data() {
  return {
    usernameText: '',
  }
  },
  methods: {
    userSubmit() {
      this.$root.$data.user = this.usernameText;
      this.$router.push('/');
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

#SignInBox {
  color: white;
  width: 60%;
  background-color: #363636;
  margin: auto;
  text-align: center;
  padding: 50px;
}

#SignInBox h2{
  text-align: left;
  margin-bottom: 0;
  padding-bottom: 0;
  padding-left: 5px;
  color: #0094bd;
}

#interface {
  width: 50%;
  margin: auto;
}

.clickButton{
  background-color: #0094bd;
  border: none;
  height: 40px;
  color: white;
  font-weight: 700;
  font-size: 22px;
  border-color: #0094bd;
  border-radius: 5px;
  outline: none;
}
.clickButton :active{
  background-color: white;
  border: none;
  height: 40px;
  color: black;
  font-weight: 700;
  font-size: 22px;
  border-color: white;
  border-radius: 5px;
  outline: none;
}

.search {
  margin: auto;
  border: 5px solid #1a1a1a;
  border-radius: 3px;
  width: 100%;
  background-color: white;
}

form {
  display: table;
  width: 100%;
}


input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 90%;
  height: 40px;
  margin-left: 2.5%;
  outline: none;
}


</style>
