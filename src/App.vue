<template>
  <div id="app">
      <meteo></meteo>
  </div>
</template>

<script>

import Meteo from './components/Meteo'


export default {
  name: 'App',
  
  components: {
    
    'meteo': Meteo
  }

}
</script>

<style>

body {
  background : #43c6ac;
  background: #8e9eab;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #eef2f3, #8e9eab);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #eef2f3, #8e9eab); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */


}

</style>
