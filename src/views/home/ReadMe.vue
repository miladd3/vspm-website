<template>
  <div class="readme" id="readme">
    <div class="container">
      <vue-showdown
        :markdown="readme"
        :options="{ ghCodeBlocks: true }"
        :extensions="[showdownHighlight]"
      />
    </div>
  </div>
</template>

<script>
import { VueShowdown } from 'vue-showdown'
import showdownHighlight from 'showdown-highlight'
import 'highlight.js/styles/default.css'
import readme from './README-src.md'

export default {
  name: 'ReadMe',
  data() {
    return { readme, showdownHighlight }
  },
  components: { VueShowdown },
  mounted() {
    // console.log(readme)
  }
}
</script>

<style lang="scss">
.readme {
  padding: 3rem 0;

  p {
    margin-bottom: 1rem;
    margin-top: 0.5rem;
  }

  code {
    background-color: #f2f2f2;
    font-family: Consolas, Monaco, Lucida Console, Liberation Mono,
      DejaVu Sans Mono, Bitstream Vera Sans Mono, Courier New, monospace;
  }
}
</style>
