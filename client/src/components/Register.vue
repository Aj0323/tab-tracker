<template>
  <div>
    <h1>Register</h1>

    <input v-model="email" type="text" name="email" placeholder="Email" id="email" />
    <br>
    <input v-model="password" type="password" name="password" placeholder="passowrd" id="password" />
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style scoped>

</style>
