<template>
  <div id="translate-form" class="translated-text">
    <h2>{{ translatedText }}</h2>
  </div>
</template>

<script>
export default {
  name: "translateOutput",
  props: ["translatedText"]
}
</script>

<style scoped>
.translated-text {
  margin-top: 10px;

}
</style>
