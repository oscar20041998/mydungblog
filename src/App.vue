<template>
  <div id="app">
    <div id="nav">
      <b-row>
        <b-col style="text-algin: left">
          <h3>SAFE AND SOUND</h3>
        </b-col>
        <b-col style="text-align: right">
          <router-link to="/"
            ><b-icon
              icon="house-fill"
              scale="1.25"
              shift-v="1.25"
              aria-hidden="true"
            ></b-icon>
            Home
          </router-link>
          | <router-link to="/about">About</router-link> |
          <!-- <router-link to="/about">Memorables</router-link> -->
        </b-col>
      </b-row>
    </div>
    <b-container fluid="lg">
      <router-view />
    </b-container>
  </div>
</template>

<style lang="scss">
body {
  height: 100%;
  width: 100%;
}

h3 {
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  color: #f3f3f3;
  box-shadow: 0 12px 6px -6px gray;
  width: fit-content;
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
  padding: 20px;
  border-bottom: solid 1px rgb(179, 177, 177);
  margin-bottom: 0.5%;
  background-color: #ffa8b6;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #f3f3f3;
      font-size: 16px;
    }
  }
}

.container-lg {
  padding: 10px;
  border: solid 1px rgb(179, 177, 177);
  overflow: auto;
  margin: 10px 0px 10px 0;
}

.img-fluid {
  max-width: 100%;
  height: 520px !important;
  max-height: 550px !important ;
}

.col {
  text-align: left;
}
</style>
