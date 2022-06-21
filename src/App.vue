<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/register">Register</router-link>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

/* CUSTOM STYLE */

.container {
  position: relative;
  left: 50%;
  width: 350px;
  max-width: 95%;
  transform: translateX(-50%);
}

.input {
  display: flex;
  flex-direction: column;
  margin-bottom: 12px;
}

.input > label {
  text-align: start;
}

.input > input {
  margin-top: 6px;
  height: 25px;
}
</style>
