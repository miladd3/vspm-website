<template>
  <div class="wrap example-custom-css">
    <label for="custom-css-input">Password</label>
    <div class="input-container">
      <input id="custom-css-input" type="password" v-model="password" />
      <password-meter :password="password" />
    </div>
  </div>
</template>

<script>
import PasswordMeter from 'vue-simple-password-meter'

export default {
  name: 'ExampleCustomCss',
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
/*
  some styles for the input
*/
.wrap {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 400px;
  margin: 40px auto;
}

input {
  border: 1px solid #ccc;
  border-radius: 0.5rem;
  width: 100%;
  padding: 10px;
  box-sizing: border-box;
}

.input-container {
  position: relative;
  display: flex;
  align-items: center;
}
</style>

<style lang="scss">
/**
    Password Meter Styles
    NOTE if you wanna change css of the password meter you should not use scoped
    you can use a parent class for better results
  */
.example-custom-css {
  .po-password-strength-bar {
    border-radius: 2px;
    transition: all 0.2s linear;
    height: 20px !important;
    width: 20px !important;
    position: absolute;
    right: 10px;
    margin-top: auto;
  }

  .po-password-strength-bar.risky {
    background-color: #f95e68;
  }

  .po-password-strength-bar.guessable {
    background-color: #fb964d;
  }

  .po-password-strength-bar.weak {
    background-color: #fdd244;
  }

  .po-password-strength-bar.safe {
    background-color: #b0dc53;
  }

  .po-password-strength-bar.secure {
    background-color: #35cc62;
  }
}
</style>
