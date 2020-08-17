<template>
  <div class="example-wrap">
    <h3>{{ title }}</h3>

    <div class="example">
      <slot></slot>
    </div>

    <div class="code-sandbox">
      <a :href="codesandboxHref" target="_blank">
        <img
          :alt="`Edit ${title}`"
          src="https://codesandbox.io/static/img/play-codesandbox.svg"
        />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ExampleWrap',
  props: {
    title: {
      type: String,
      default: ''
    },
    codesandboxHref: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
.example-wrap {
  padding: 50px 0;
  border-bottom: 1px solid #f2f2f2;
}

h3 {
  color: #888888;
  text-align: center;
  margin-bottom: 0 !important;
}

.code-sandbox {
  text-align: center;
}
</style>
