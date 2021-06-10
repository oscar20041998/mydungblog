<template>
  <div id="app">
    <h3>Mỹ Dung blog</h3>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/about">Memorables</router-link>
    </div>
    <div class="container">
      <router-view />
    </div>
  </div>
</template>

<style lang="scss">
body {
  height: 100%;
  width: 100%;
}

h3 {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif
}

.footer-copyright {
  margin-top: 0.5%;
  border-top: solid 1px rgb(179, 177, 177);
  position: absolute;
  width: 100%;
  bottom: 0;
}

#app {
  font-family: "Times New Roman", Times, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

a:hover {
  font-size: 18px;
  transition: all 0.5s;
  opacity: 0.3;
  margin-right: 15px;
  margin-left: 15px;
}

#nav {
  padding: 30px;
  border-bottom: solid 1px rgb(179, 177, 177);
  margin-bottom: 0.5%;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

.container {
  padding: 10px;
  border: solid 1px rgb(179, 177, 177);
  overflow: auto;
  margin: 10px 0px 10px 0;
}
</style>
