<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
*, *:before, *:after {
  box-sizing: border-box;
}

html, body {
  height: 100%;
  overscroll-behavior: none;
}

body {
  margin: 0; padding: 0;
}

a {
  color: #fff;
  text-decoration: none;
}

.bg-blue {
  background: rgb(13,53,85);
  background: linear-gradient(346deg, rgba(13,53,85,1) 10%, rgba(26,112,175,1) 56%, rgba(100,125,171,1) 94%);
}

.bg-green {
  background: rgb(51,121,90);
  background: linear-gradient(347deg, rgba(51,121,90,1) 22%, rgba(78,163,152,1) 50%, rgba(24,200,170,1) 82%);
}

.bg-red {
  background: rgb(85,13,84);
  background: linear-gradient(346deg, rgba(85,13,84,1) 10%, rgba(175,26,52,1) 56%, rgba(171,100,119,1) 94%);
}

.bg-black {
  background: rgb(68,61,87);
  background: linear-gradient(346deg, rgba(68,61,87,1) 10%, rgba(63,71,92,1) 56%, rgba(17,17,23,1) 94%);
}

#app {
  font-family: sans-serif;
  font-weight: 300;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  user-select: none;
  text-align: center;
  color: #fff;
}
</style>
