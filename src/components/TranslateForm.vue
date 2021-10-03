<template>
  <div  id="translateForm">
      <div class="col-md-6 col-md-offset-3">
      <form class="search-box"  @submit.prevent="formSubmit">
       <input class="form-control" type="text" v-model="textToTranslate" placeholder="enter a word">
       <br>
       <input class="btn btn-secondary" type="submit" value="translate">
      </form>
  </div>
  </div>
</template>
<script>
export default {
    name: 'translateForm',
    data() {
        return {
         textToTranslate: '', 
         language:'',
        }
    },
    methods:{
        formSubmit(e){
            this.$emit('formSubmit',this.textToTranslate)
           
        }
    }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-family: 'monserrat', sans-serif;
}
#translateForm{
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;
}
.search-box{
  widows: 100%;
  margin-bottom: 30px;
}
.search-box{
  display: block;
  width: 100%;
  padding: 15px;
  color: #313131;
  font-size: 20px;
  appearance: none;
  border: none;
  outline: none;
  background: none;
  box-shadow: 0px 0px 8px rgba(0,0,0,0.25);
  background-color: rgba(255,255,255,0.5);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}
.search-box:focus{
  box-shadow: 0px 0px 16px rgba(0,0,0,0.25);
 background-color: rgba(255,255,255,0.75);
 border-radius: 16px 0px 16px 0px;
}

</style>