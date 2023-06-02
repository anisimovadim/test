<template>
  <div>
    <h1>Register</h1>

    <input type="email"
           name="email"
           v-model="email"
           placeholder="email">
    <input type="password"
           name="password"
           v-model="password"
           placeholder="password">
    <button @click="register">Зарегистрироваться</button>
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
div{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}
</style>
