<template>
  <div class="row" id="translate-form">
    <div class="col-md-6 offset-md-4">
      <form id="transForm" class="form-inline well" @submit="formSubmit">
        <input type="text" class="form-control" v-model="textToTranslate" placeholder="Enter a word...">
        <select class="form-control" v-model="language">
          <option value="hi">Hindi</option>
          <option value="mr">Marathi</option>
          <option value="bn">Bengali</option>
          <option value="pa">Punjabi</option>
          <option value="ta">Tamil</option>
        </select>
        <input class="btn btn-primary" type="submit" value="Translate">
      </form>
    </div>
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
#transForm{
  border-radius:10px;
}
</style>
