<template>
  <div class="main-examples" id="main-examples">
    <div class="container">
      <h2>Examples</h2>

      <example-wrap
        title="Simple Usage"
        codesandbox-href="https://codesandbox.io/s/simple-example-for-vspm-1z2f4=/src/App.vue"
      >
        <example-simple />
      </example-wrap>

      <example-wrap
        title="With custom css"
        codesandbox-href="https://codesandbox.io/s/vspm-with-custom-css-ngysz?file=/src/App.vue"
      >
        <example-custom-css />
      </example-wrap>

      <example-wrap
        title="Use with emojies"
        codesandbox-href="https://codesandbox.io/s/vspm-use-with-emojies-go60c?file=/src/App.vue"
      >
        <example-emojies />
      </example-wrap>
    </div>
  </div>
</template>

<script>
import ExampleSimple from './examples/ExampleSimple'
import ExampleCustomCss from './examples/ExampleCustomCss'
import ExampleEmojies from './examples/ExampleEmojies'
import ExampleWrap from './ExampleWrap'
export default {
  name: 'MainExamples',
  components: { ExampleWrap, ExampleEmojies, ExampleCustomCss, ExampleSimple }
}
</script>

<style scoped></style>
