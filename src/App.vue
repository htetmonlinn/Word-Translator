<template>
  <div class="text-center" id="app">
     <h1>Word Translator</h1>
     <h5>Power by Vue.js</h5>
     <TranslateForm @formSubmit="translateText"></TranslateForm>
     <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>
<script>
import TranslateOutput from './components/TranslateOutput'
import TranslateForm from './components/TranslateForm'
import axios from 'axios'
export default {
  components: {
    TranslateOutput, TranslateForm },
  name: 'app',
  data() {
    return {
      translatedText: '',
      
      
      
    }
  },
  methods:{
   translateText(text){
     axios.get(`https://www.dictionaryapi.com/api/v3/references/sd4/json/${text}?key=702e0eac-f291-4e28-8949-be0226b6ce90&lang:ru`)
     .then(res => {
       this.translatedText= res.data[0].shortdef[0];
       
     })
     .catch((error) => {
       console.log(error);
     });
    }
  }
}
</script>

<style>

</style>
