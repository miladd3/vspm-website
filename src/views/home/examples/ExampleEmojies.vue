<template>
  <div class="wrap example-emojies">
    <label>Password</label>
    <input type="password" v-model="password" />
    <password-meter :password="password" />
  </div>
</template>

<script>
import PasswordMeter from 'vue-simple-password-meter'

export default {
  name: 'ExampleEmojies',
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
  position: relative;
}

input {
  border: 1px solid #ccc;
  border-radius: 0.5rem;
  width: 100%;
  padding: 10px;
  box-sizing: border-box;
}
</style>

<style lang="scss">
/**
  Password Meter Styles
  NOTE if you wanna change css of the password meter you should not use scoped
  you can use a parent class for better results
*/
.example-emojies {
  .po-password-strength-bar {
    border-radius: 2px;
    transition: all 0.2s linear;
    position: absolute;
    right: 10px;
    font-size: 20px;
    margin-top: auto;
    width: auto !important;
    top: 30px;
    background-color: transparent !important;
  }

  .po-password-strength-bar.risky {
    &:before {
      content: '😱';
    }
  }

  .po-password-strength-bar.guessable {
    &:before {
      content: '😣';
    }
  }

  .po-password-strength-bar.weak {
    &:before {
      content: '🤨';
    }
  }

  .po-password-strength-bar.safe {
    &:before {
      content: '🙂';
    }
  }

  .po-password-strength-bar.secure {
    &:before {
      content: '😁';
    }
  }
}
</style>
