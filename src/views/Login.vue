<template>
  <div id="login-page" class="container">
    <form @submit.prevent="login" class="form-login">
      <div>
        <img src="../assets/home.jpg" class="front-img" height="550px">
      </div>
      <div class="form-group mt-3">
        <label for="exampleInputEmail1">Email address</label>
        <input v-model="email" type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
      </div>
      <div class="form-group mt-3">
        <label for="exampleInputPassword1">Password</label>
        <input v-model="password" type="password" class="form-control" id="exampleInputPassword1">
      </div>
      <div class="d-grid gap-2">
        <button type="submit" class="btn btn-dark mt-3"><i class='fas fa-sign-in-alt'></i>Login</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login () {
      const payload = {
        email: this.email,
        password: this.password
      }
      this.$store.dispatch('login', payload)
    }
  }
}
</script>

<style>
  #login-page {
    font-family: 'Metal Mania', cursive;
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-top: 3%;
    margin-bottom: 5%;
  }
</style>
