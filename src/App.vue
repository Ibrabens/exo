<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
   
      <nav>
        <ul>
        <li> <RouterLink to="/">Home</RouterLink></li>
        <li><RouterLink to="/posts">Posts</RouterLink></li>
       <li> <RouterLink to="/user">User</RouterLink> </li>
       <li> <RouterLink to="/bitcoin">Bitcoin</RouterLink> </li>
        </ul>
      </nav>
  </header>

  <RouterView />
</template>


<style scoped>
ul{
    list-style-type: none;
    text-align: center;
    margin: 0;
}
li{
    display: inline-block;
    margin: 0 10px;
}
a{
    color: #fff;
    text-decoration: none;
    padding: 6px 8px;
    border-radius: 10px;
}
nav{
    background: #444;
    padding: 14px 0;
    margin-bottom: 40px;
}
.router-link-active{
    background: #eee;
    color: #444;
}
</style>

