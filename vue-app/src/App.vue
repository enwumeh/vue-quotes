<template>
<div id="app">
  <main>
    <div class="quotes-title"> Quotes App

    </div>
    <div class="search-box">
      <input type="text" class="search-bar" placeholder="Find a quote">
      <button>Find!</button>
    
      </div>
      <div class="quotes-wrap">

      </div>


  </main>
  </div>
</template>

<script>
import quotes from './components/quotes.js'

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
