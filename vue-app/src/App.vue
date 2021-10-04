<template>
  <div id="app">
    <main>
      <div class="quotes-title">Quotes Finder App</div>
      <Quotes/>
    </main>
  </div>
</template>

<script>
import Quotes from "./components/Quotes";
export default {
  name: "App",
  components: {
    Quotes
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.quotes-title {
  font-family: Andale Mono, monospace;
  font-size: 8vh;
  text-align: center;
  color: rgb(22, 21, 21);
}
#app {
  margin: 0;
}
</style>
