# Getting started

**Vue Simple Password Meter** is a simple password checker written in vanilla js and extremely lightweight (**3.2kb minified + Gzipped**)

#### This is `Vue 3.*` compatible version. If you are using `Vue 2.*` [Click Here](https://github.com/miladd3/vue-simple-password-meter#readme)

## Install

`npm install vue-simple-password-meter@next --save`

## Usage

Simply use v-model and send it to the component using password prop

```vue
<template>
  <div id="app">
    <label>Password</label>
    <input type="password" v-model="password" />
    <password-meter :password="password" />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import PasswordMeter from 'vue-simple-password-meter';

export default defineComponent({
  components: {
    PasswordMeter,
  },
  setup() {
    const password = ref('');

    return {
      password,
    };
  },
});
</script>
```

### Customize using css

If you want to customize the bar its really simple with some easy css you can customize it

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
  <div id="app">
    <label>Password</label>
    <input type="password" v-model="password" />
    <span v-if="score === 0">Use better password</span>
    <password-meter @score="onScore" :password="password" />
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import PasswordMeter from "vue-simple-password-meter";

export default defineComponent({
  name: "App",
  components: {
    PasswordMeter,
  },
  setup() {
    const password = ref("");
    const score = ref(null);

    const onScore = (payload) => {
      console.log(payload.score); // from 0 to 4
      console.log(payload.strength); // one of : 'risky', 'guessable', 'weak', 'safe' , 'secure'
      score.value = payload.score;
    };

    return {
      password,
      onScore,
      score,
    };
  },
});
</script>
```
