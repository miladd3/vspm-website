# Getting started

**Vue Simple Passwod Meter** is a simple password checker written in vanilla js and extremly lightweight (**3.2kb minified + Gzipped**)


## Install

`npm install vue-simple-password-meter --save`

## Usage

Simply use v-model and send it to the component using password prop

```vue
<template>
  <form>
    <label for="password">Password</label>
    <input id="password" type="password" v-model="passwordValue" />
    <password-meter :password="passwordValue" />
  </form>
</template>

<script>
import passwordMeter from "vue-simple-password-meter";

export default {
  components: { passwordMeter },
  data: () => ({
    passwordValue: null
  })
};
</script>
```

### Customize using css

If you wanna customize the bar its really simple with some easy css you can customize it

Overwrite these css styles globally and change each state color and style

```css
.po-password-strength-bar {
  border-radius: 2px;
  transition: all 0.2s linear;
  height: 5px;
  margin-top: 8px;
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
```

## Events

You can use event `score` to use scored number between `0` to `4` that scores password from risky to secure with 4 is a secure password and 0 is risky and between.

You can use this as a form verification tool

See below example for more detail

```vue
<template>
  <form>
    <label for="password">Password</label>
    <input id="password" type="password" v-model="passwordValue" />
    <span v-if="score === 0">Use better password</span>

    <password-meter :password="passwordValue" @score="onScore" />
  </form>
</template>

<script>
import passwordMeter from "vue-simple-password-meter";

export default {
  components: { passwordMeter },
  data: () => ({
    passwordValue: null,
    score: null
  }),
  methods: {
    onScore({ score, strength }) {
      console.log(score); // from 0 to 4
      console.log(strength); // one of : 'risky', 'guessable', 'weak', 'safe' , 'secure' 
      this.score = score;
    }
  }
};
</script>
```


