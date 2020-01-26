<template>
  <div class="text-center container" id="app">
    <h1>Word Translator</h1>
    <h5 class="text-muted">Powered By Vue.js</h5>
    <hr>
    <translate-form @formSubmit="translateText"></translate-form>
    <translate-output v-text="translatedText"></translate-output>
  </div>
</template>

<script>
import TranslateForm from "./components/TranslateForm";
import TranslateOutput from "./components/TranslateOutput";

export default {
  name: 'app',
  data() {
    return {
      translatedText: "",
      api_key: "trnsl.1.1.20200126T053110Z.3db468c07704299b.37e7fdcbfe5ad7fff7f5474e84ef698a5db93a63"
    }
  },
  components: {
    TranslateForm,
    TranslateOutput
  },
  methods: {
    translateText(text, language) {
      this.$http.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=${this.api_key}&lang=`+language+`&text=`+text)
        .then(response => {
          this.translatedText = response.body.text[0];
        });
    }
  }
}
</script>

<style>
body {
  background:#fefefe;
  margin: auto;
  padding: auto;
}
</style>
