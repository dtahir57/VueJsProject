<template lang="html">
  <div class="register">
    <h1>Register</h1>
    <input type="email" name="email" placeholder="Email" v-model="email" />
    <input type="password" name="password" placeholder="Password" v-model="password" />
    <button type="submit" @click="register">Register</button>
  </div>
</template>

<script>
import Auth from '@/services/auth'
export default {
  name: 'Register',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register() {
      const response = await Auth.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style lang="css">
</style>
