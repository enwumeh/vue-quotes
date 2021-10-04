<template>
  <div class="quotes">
    <div class="search-box">
      <input type="text" id='user-input' class="search-bar" placeholder="Find a quote" />
      <button class="search-button" v-on:click="filtered = searchResults(set)">Search</button>
    </div>
    <div class="quotes-main">
      <div class="data">
        <ul class="list-quotes">
            
            <div class="filter">
              <button class="movie filter-button" v-on:click="filtered = showMovies(set)">MOVIES</button>
               <button class="game filter-button" v-on:click="filtered = showGames(set)">GAMES</button>
            </div>
          <li class="" v-bind:key="element.quote" v-for="element in filtered.slice(15*currentPage, 15*(currentPage + 1))">
            <div class="quote-section">
           <h1 class="quote-source">From: {{ element.source }} </h1>
           <br>
           <h2 class="quote-word">Quote:</h2>
           <h3 class="quote-text">{{ element.quote }}</h3>
            </div>
            <br>
            </li>
            <div class="navigation">
              <button class="left-nav nav" v-on:click="currentPage >= 0 ? currentPage-=1 : currentPage = currentPage + 0">← </button>
               <button class="right-nav nav" v-on:click="currentPage >= 0 ? currentPage = currentPage + 1 : currentPage= currentPage + 0">→ </button>
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
      currentPage: 0
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
  const input = document.getElementById('user-input').value.toLowerCase();
  return set.filter((element) => element.quote.toLowerCase().includes(input));
},
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

* {
 font-family: Andale Mono, monospace		
}
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
.quote-source {
padding-top: 10%;
color: rgb(45, 8, 8);
font-size: 3vh;
}

.quote-text {
color: rgb(230, 230, 230);
font-size: 2.5vh;
font-weight: 200;
height: 80%;
padding-bottom: 4vh;

}

.quote-section {
  display: in-line block;
  height: 45vh;
  width: 30vh;
background-color: rgb(52, 117, 142);
border-radius: 15px;
margin: 1.3vh;
}

.quote-word {
color: rgb(229, 225, 225);
font-size: 2.5vh;
}


.search-box {
  text-align: center;
  font-size: 4vh;
  height: 4vh;

}

#user-input {
  height: 4vh;
  font-size: 3vh;
}

.search-button {
  height: 4vh;
  color: white;
  background-color: rgb(44, 42, 42);
  left: 4%;
  font-size: 2.5vh;
  border-radius: 15%;
  position: relative;
}

.filter {
position: relative;
margin: 0 auto;
}

.filter-button{
background-color: rgba(200, 200, 210, 0.525);
height: 6vh;
width: 15%;
color: rgb(32, 29, 29);
margin: 2vh;
font-size: 3vh;
border-radius: 15px;
border: none;

}

.nav {
  color: rgb(122, 116, 116);
  border:none;
  font-size:34vh;
  height: 10vh;
  width:10vh;
  font-weight: bold;
}

.right-nav {
position:relative;
left: 20%;
}

.left-nav {
position:relative;
left: -20%;
}

</style>
