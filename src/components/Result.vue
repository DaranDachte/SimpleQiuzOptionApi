<template>
  <div class="result">
    <div class="title">{{ results[resultIndex].title }}</div>
    <div class="desc">{{ results[resultIndex].desc }}</div>
  </div>
</template>

<script lang="ts">
export default {
  props: ['results', 'totalCorrect'],
  computed: {
    resultIndex() {
      let index = 0

      this.results.forEach((e: { min: number; max: number }, i: number) => {
        if (e.min <= this.totalCorrect && e.max >= this.totalCorrect) {
          index = i
        }
      })
      return index
    }
  }
}
</script>

<style scoped></style>
