<template>
  <div id="app">
    <header>
      <span>vue-pwa-demo</span>
      <div>
        <a href="#/">Home</a>
        <a href="#/notes">Notes</a>
      </div>        
    </header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
body{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 1em;
}

header {
  background-color: darkblue;
  text-align: right;
  color: #fff;
  padding: 1em 2em;
  font-weight: bold;
  overflow: hidden;
}

header div {
  text-align: left;
  float:left;
}

header div a {
  margin: 0 1em 0 0;
  color: #cdf;
  font-weight: normal;
}

header div a:hover {
  text-decoration: underline;
}

main{
  margin: 2em;
}

h1 {
  padding: 0;
}
</style>
