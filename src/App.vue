<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <router-view/>
  </div>
</template>

<style>
nav {
  background-color: #f0f0f0;
  padding: 1rem;
}

nav a {
  margin-right: 1rem;
  text-decoration: none;
  color: #333;
}

nav a.router-link-active {
  color: #42b983;
}
</style>