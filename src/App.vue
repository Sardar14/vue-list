<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>
<template>
<div class="container-fluid">
     <nav class="navbar navbar-expand-sm navbar-light bg-light shadow-sm">
         <div class="container">
         <a class="navbar-brand" href="#">Navbar</a>
         <button class="navbar-toggler d-lg-none" type="button" data-bs-toggle="collapse" data-bs-target="#collapsibleNavId" aria-controls="collapsibleNavId"
           aria-expanded="false" aria-label="Toggle navigation">
           <span class="navbar-toggler-icon"></span>
         </button>
         <div class="collapse navbar-collapse" id="collapsibleNavId">
           <ul class="navbar-nav me-auto mt-2 mt-lg-0">
             <li class="nav-item">
                  <router-link to="/" class="nav-link active" href="#" aria-current="page">Home</router-link> 
                  <span class="visually-hidden">(current)</span>
             </li>
             <li class="nav-item">
                 <router-link class="nav-link" to="/about">About</router-link> 
             </li>
              <li class="nav-item">
                 <router-link class="nav-link" to="/test">todo list</router-link> 
             </li>
           </ul>
  
         </div>
       </div>
     </nav>

<div class="container">
     <RouterView />
</div>
</div>

</template>

<style>
body{
  background-color:#dfd8d8;
}
</style>
