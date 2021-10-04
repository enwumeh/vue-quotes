<template>
  <div class="quotes">
    <div class="search-box">
      <input type="text" id="user-input" class="search-bar" placeholder="Find a quote" />
      <!-- <button>Find!{{ set }}</button> -->
    </div>
    <div class="quotes-main">
      <div class="data">
        <!-- {{ set }} 'to the left' -->
        <ul class="list-quotes">
            
            <div class="filter">
              <button class="movie filter-button" v-on:click="filtered = showMovies(set)">MOVIES</button>
               <button class="game filter-button" v-on:click="filtered = showGames(set)">GAMES</button>
            </div>
          <li v-for="element in filtered" v-bind:key="element.quote">
            <div class="quote-section">
           <h1 class="quote-source"> {{ element.source }}</h1>
            <br>
           <div class="quote-text">{{ element.quote }}</div>
            </div>
            <br>
            </li>
            <div class="navigation">
              <button class="nav">← </button>
               <button class="nav">→ </button>
            </div>
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
  data:  () => {
    return {
      set: quoteList,
      filtered: quoteList,
      currentPage: "CURRENT PAGE IS FINE"
    }
  }, 
  methods: {
showMovies: (set) => {
  return set.filter((element) => element.theme == "movies");
}, 
showGames: (set) => {
  return set.filter((element) => element.theme == "games");
},
searchResults: (set) => {
  const input = document.getElementById('user-input');
  return set.filter((element) => element.quote.includes(input));
},
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

.quotes-main {
text-align:center;
}
/* .quote-source {
color: brown;
} */

/* .quote-text {
color: rgb(37, 7, 7);
font-size: 2.5vh;
} */

.quote-section {
background-color: rgb(29, 182, 67);
/* font-size: 2.9vh; */
}

.search-box {
  text-align: center;
}

.filter {
position: relative;
margin: 0 auto;
}

.filter-button{
background-color: blue;
height: 6vh;
width: 15%;
color: white;
margin: 2vh;
border-radius: 15px;

}

.nav {
  color: black;
  font-size:9vh;
  height: 10vh;
  width:10vh;
}
</style>
