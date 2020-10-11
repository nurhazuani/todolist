<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
      <router-link to="/todo">Todo</router-link>
    </div>
    <router-view /> -->
<head>
   <link href="https://fonts.googleapis.com/css?family=Baloo+Bhai|Candal|Chewy&display=swap" rel="stylesheet">
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
</head>
      <todo-list list-name="TO-DO LIST" />
    
  </div>
</template>

<script>

import TodoList from "./views/TodoList.vue";

export default {

 name: "App",
  components: {
    TodoList,
  },

  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
