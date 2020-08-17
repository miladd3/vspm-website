<template>
  <div class="page-home">
    <hero-main />
    <read-me />
    <main-examples />
  </div>
</template>

<script>
import HeroMain from './HeroMain'
import ReadMe from './ReadMe'
import MainExamples from './MainExamples'
export default {
  name: 'HomePage',
  components: { MainExamples, ReadMe, HeroMain }
}
</script>

<style scoped></style>
