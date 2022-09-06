<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '@/components/HelloWorld.vue'
import AboutView from '@/views/AboutView.vue'
</script>

<template>
  <header>

    <div>
      <h1>Cuenta cuentos</h1>
      <AboutView/>
    </div>
  </header>

  
</template>

<style>
@import '@/assets/base.css';

#app  {
  font-size: 25px;
  font-family: 'Avenir';
  margin: auto;
  width: 80%;
  padding: 10px;
  
}
  

  

  
  

  

</style>
