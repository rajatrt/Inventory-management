<template>
  <div class="register-wrapper">
    <h1>Register</h1>
    <input type="text"
    v-model="userName"
    placeholder="User Name"/>
    <input type="password"
    v-model="password"
    placeholder="Password"/>
    <button @click="registerUser">Register</button>
  </div>
</template>
<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      userName: '',
      password: null
    }
  },
  methods: {
    async registerUser () {
      console.log('hi i am hit')
      await AuthenticationService.register({
        email: this.userName,
        password: this.password
      })
    }
  }
}
</script>
<style>
  .register-wrapper{
    display: flex;
    flex-direction: column;
    background-color: cyan;
  }
</style>
