<template>
  <div class="wrap example-simple">
    <label>Password</label>
    <input type="password" v-model="password" />
    <password-meter :password="password" />
  </div>
</template>

<script>
import PasswordMeter from 'vue-simple-password-meter'

export default {
  name: 'ExampleSimple',
  components: {
    PasswordMeter
  },
  data() {
    return {
      password: null
    }
  }
}
</script>

<style scoped lang="scss">
.wrap {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 400px;
  margin: 20px auto;
}

input {
  border: 1px solid #ccc;
  border-radius: 0.5rem;
  width: 100%;
  padding: 10px;
  box-sizing: border-box;
}
</style>
