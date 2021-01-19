<template>
  <div class="flex h-screen items-center justify-center bg-gray-100">
    <!-- quiz container -->
      <quizContainer/>
  </div>
</template>

<script>
import quizContainer from '../components/quizContainer'
export default {
  components: {
    quizContainer
  }
}
</script>

<style scoped>
.neumorph-1 {
  box-shadow: 6px 6px 18px rgba(0, 0, 0, 0.09), -6px -6px 18px #ffffff;
}
.container {
  max-width: 600px;
  border-radius: 25px;
}
</style>
