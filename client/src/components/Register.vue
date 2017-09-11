<template lang="pug">
  div
    h1 Register
    hr
    input(type="text", name="username", placeholder="Username or Email", v-model="username")
    br
    input(type="password", name="password", placeholder="Password" v-model="password")
    br
    button(@click="login") Login
</template>

<script>
import AuthService from '@/services/AuthService'

export default {
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    async login () {
      const res = await AuthService.login({
        username: this.username,
        password: this.password
      })
      console.log('login-ok', res.data)
    }
  }

}
</script>

<style lang="stylus" scoped>

</style>
