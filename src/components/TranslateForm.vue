<template>
  <div id="translate-form">
    <form @submit="formSubmit">
      <input type="text" v-model="textToTranslate" placeholder="Enter a word...">
      <select v-model="language">
        <option value="hi">Hindi</option>
        <option value="mr">Marathi</option>
        <option value="bn">Bengali</option>
        <option value="pa">Punjabi</option>
        <option value="ta">Tamil</option>
      </select>
      <input type="submit" value="Translate">
    </form>
  </div>
</template>

<script>
export default {
  name: "translateForm",
  data() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  created() {
    this.language = "hi";
  },
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>
</style>
