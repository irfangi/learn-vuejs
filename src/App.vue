<template>
  <div id="app">
    <div id="nav">
      <router-link to="/" class="link">Home</router-link> |
      <router-link to="/about" class="link">About</router-link> |
      <router-link to="/event" class="link">Event</router-link> |
    </div>
    <div class="content">
      <router-view />
    </div>
  </div>
</template>

<style>
#app {
  width: 100%;
}
#nav {
  padding: 12px;
  border: 1px solid green;
  display: flex;
  overflow: auto;
  justify-content: center;
}
.link {
  margin: 0 12px;
  text-decoration: none;
  color: black;
  font-weight: 400;
}
.content {
  display: flex;
  padding: 12px;
  justify-content: center;
}
.router-link-exact-active {
  text-decoration: underline;
  font-weight: 800;
}
.main {
  width: 100vw;
}
.container {
  width: 80%;
  margin: 0 auto;
}
.list-content {
  margin-bottom: 25px;
  border-top: 1px solid rgb(46, 46, 46);
}
.mt-4 {
  margin-top: 2rem;
}
</style>
