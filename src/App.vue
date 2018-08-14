<template>
  <div id="app" class="text-center">
    <h1>Word Translator</h1>
    <img class="rogue-logo" src="./assets/logo.png" alt="rogue-logo">
    <p>Coded by <span id="handle">@codebreakerjulia</span></p>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <div class="translate-output">
      {{translatedText}}
    </div>

    <!-- <TranslateOutput v-text="translatedText"></TranslateOutput> -->
    <p>Tutorial by Traversy Media<br>Powered by Vue.js</p>
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
      translatedText: 'Translation will go here...'
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
body {
  margin-top: 30px;
  background: #fefefe;
}
.rogue-logo{
  margin-bottom: 5px;
  width: 80px;
}
#handle {
  color: #317EC6;
}
.translate-output {
  border-radius: 10px;
  border: 2px #317EC6 solid;
  background-color:#3E99ED;
  padding: 10px;
  margin: 15px;
}
</style>
