<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered by Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm';
import TranslateOutput from './components/TranslateOutput';

export default {
  name: 'App',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText: function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180812T235045Z.676b1bc879c58241.d1cbad01d155a87fec2d08f726d7f4bee08d6592&lang='+language+'&text='+text).then((response) => {
        this.translatedText = response.body.text[0];
        console.log(response);
      });
    }
  }
}
</script>

<style>
#app {

}
</style>
