<template>
  <div id="app">
    <header>
      <span>vue-pwa-demo</span>
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
  font-size: 1.5em;
}

header {
  background-color: darkblue;
  text-align: right;
  color: #fff;
  padding: 1em 2em;
  font-weight: bold;
}

main{
  margin: 2em;
}
</style>
