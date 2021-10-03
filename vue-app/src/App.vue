<template>
<div id="app">
  <main>
    <div class="quotes-title"> Quotes Finder App
     
    </div>
    


  </main>
  </div>
</template>

<script>
import quotes from './quotes.js'

export default {
  name: 'App',
  data () {
    return {
      quotesData: quotes
    }
    
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
    margin: 0;
}
</style>
