<template>
  <h2>问题1</h2>
  <br>
  <QuestionOne />
  <br>
  <h2>问题2</h2>
  <br>
  <QuestionTwo />
  <br>
  <h2>问题3</h2>
  <br>
  <QuestionThree/>
  <br>
  <h2>问题4</h2>
  <br>
  <QuestionFour />
</template>

<script>
import QuestionFour from './components/QuestionFour.vue';
import QuestionOne from './components/QuestionOne.vue'
import QuestionThree from './components/QuestionThree.vue';
import QuestionTwo from './components/QuestionTwo.vue'

export default {
  data() {
    return {
    }
  },
  components: {
    QuestionOne,
    QuestionTwo,
    QuestionThree,
    QuestionFour
  }
}
</script>

<style scoped>

</style>
