<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered by Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm';

export default {
  name: 'App',
  components: {
    TranslateForm
  },
  methods: {
    translateText: function(text){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180812T235045Z.676b1bc879c58241.d1cbad01d155a87fec2d08f726d7f4bee08d6592&lang=ru&text='+text).then((response) => {
        console.log(response)
      });
    }
  }
}
</script>

<style>
#app {

}
</style>
