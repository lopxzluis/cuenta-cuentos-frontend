<script>
  import axios  from 'axios'

  export default {
  data(){
    return{
      text: "",
      textOpenai: "Había una vez",
    }
  },
  methods:{
    formulario(){
      this.textOpenai = this.textOpenai + " " + this.text
      this.text = ""
      var ctx = this;
      axios.post("https://nkj46zl4fj.execute-api.us-east-1.amazonaws.com/dev/autocompletar", {texto: this.textOpenai})
      .then(function(response){
        ctx.textOpenai = response.data.respuesta_openai
      })
      .catch(function (error){
        console.warn(error)
        alert("Tu conexión falló, revisa tu internet")
      });


    }
  }
 } 
</script>

<template>
  <div class="text-openai" >
    <h3>{{textOpenai}}</h3>
    <br>
     <form action class="form" @submit.prevent="formulario">
      <input
        v-model="text"
        class="form-input"
        type="text"
        id="text"
        placeholder="Continua el cuento:"
      >
      <input class="form-submit" type="submit" value="Enviar" >
    </form>
  </div>
</template>

<style>

.text-openai  {
  text-align: justify;
  color: #001A20 ;
  font-size: 20px;
  padding-top: 29px;
}
.form-input{
  color: #001A20 ;
  font-size: 18px;
  width: 300px;
  height: 38px;
  background: #D7D4FF;
   border: 2px solid #393939;
   border-radius: 15px 15px 15px 15px;
}
.form-submit{
  font-size: 18px;

  color:  #001A20 ;
  width: 80px;
  height: 38px;
  border-radius: 15px 15px 15px 15px;
}
</style>
