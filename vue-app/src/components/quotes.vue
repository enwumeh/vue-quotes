<template>
  <div class="quotes">
    <div class="search-box">
      <input type="text" class="search-bar" placeholder="Find a quote" />
      <!-- <button>Find!{{ set }}</button> -->
    </div>
    <div class="quotes-main">
      <div class="data">
        <!-- {{ set }} 'to the left' -->
        <ul class="list-quotes">
          <li v-for="element in filtered" v-bind:key="element.quote">
            <div class="quote-section">
           <h1 class="quote-source"> {{ element.source }}</h1>
            <br>
           <div class="quote-text">{{ element.quote }}</div>
            </div>
            <br>
            </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
let module = require('../quotes.js');
let quoteList = module.quoteList;

export default {
  name: 'Quotes',
  data (){
    return {
      set: quoteList,
      filtered: quoteList,
      currentPage: "CURRENT PAGE IS FINE"
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.quote-source {
color: brown;
}

.quote-text {
color: rgb(37, 7, 7);
font-size: 2.5vh;
}

.quote-section {
background-color: rgb(29, 182, 67);
font-size: 2.5vh;
}
</style>
