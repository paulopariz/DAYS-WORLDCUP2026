<template>
  <div>
    <div class="bg">
      <h1>WORLD CUP 2026</h1>
      <AppCore />
    </div>
  </div>
</template>

<script>

import AppCore from './components/AppCore.vue'
export default {
  name: 'App',
  components: { AppCore
  },
};
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}


.bg{
  font-family: 'Roboto Mono', monospace;
  color: #ffffff;
  background-image: url('../src/assets/bg.jpeg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  width: 100vw;
  height: 100vh;
  position: relative;
}

h1{
  text-align: center;
  font-size: 3.875rem;
  padding-top: 30px;
}

@media(max-width: 620px){
    h1{
        font-size: 2.75rem;
    }
  }
@media(max-width: 440px){
  h1{
    font-size: 2rem;
  }
}
</style>
