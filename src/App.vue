<template>
  <div class="mx-auto" style="width: 40%">
    <form @submit.prevent="onSubmit()">
      <div class="form-group">
        <label for="exampleInputEmail1">Email address</label>
        <input
          type="email"
          class="form-control"
          aria-describedby="emailHelp"
          placeholder="Enter email"
          v-model="register.email"
        />
      </div>
      <div class="form-group">
        <label for="exampleInputEmail1">first</label>
        <input
          type="text"
          class="form-control"
          aria-describedby="emailHelp"
          placeholder="Enter name"
          v-model="register.firstname"
        />
      </div>
      <div class="form-group">
        <label for="exampleInputEmail1">last</label>
        <input
          type="text"
          class="form-control"
          aria-describedby="emailHelp"
          placeholder="Enter name"
          v-model="register.lastname"
        />
      </div>
      <div class="form-group">
        <label for="exampleInputPassword1">Password</label>
        <input
          type="password"
          class="form-control"
          placeholder="Password"
          v-model="register.password"
        />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import axios from 'axios';

export default {
  name: "App",
  data() {
    return {
      register: {
        email: 'ayobami@gmail.com',
        firstname: '',
        lastname: '',
        password: '',
        id: 122594659
      }
    };
  },

  methods: {
    onSubmit() {
      axios.post('https://mysql-golang-app.herokuapp.com/user/register', this.register)
      .then(function (response) {
        console.log(response);
      })
      .catch(function (error) {
        console.log(error);
      });
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
