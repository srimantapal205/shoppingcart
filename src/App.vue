<template>
  <nav id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/cart">Cart</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  background-color: rgba(245, 245, 245, 1); 
}
#nav {
  padding: 10px;
  width: 100%;
  height: 50px;
  background-color:rgba(240, 240, 240, 1) ;
  line-height: 30px;
  a{
    text-decoration: none;
    font-weight: 600;
    color: rgb(185, 43, 0) ;
    border-bottom: 2px solid transparent;
    margin: 0 10px;
    &.router-link-exact-active,
    &:hover{
      color: rgb(61, 14, 0) ;
      border-color: rgb(185, 43, 0);
    }
  }
}
</style>
