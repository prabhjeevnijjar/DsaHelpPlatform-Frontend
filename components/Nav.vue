<template>
<div class ="base">
  <div class="navbar1">
    <ul>
      <li><a><NuxtLink to="/">DSAFinder</NuxtLink></a></li>
    </ul>
  </div>
  <div class="navbar2">
    <ul>
      <li><a><NuxtLink to="/recommend">Recommend</NuxtLink></a></li>
      <li><a ><NuxtLink to="/">Homepage</NuxtLink></a></li>
      <li><a ><NuxtLink to="/signup">Sign Up</NuxtLink></a></li>
      <li><a ><NuxtLink to="/signin">Login</NuxtLink></a></li>    
    </ul>
  </div>
</div>
</template>

<style scoped>
.base{
  display:flex;
  justify-content: space-between;
  background-color: #B33F50;
  border-radius:50px;
  font-size:16px;
  margin:0 auto;
  width:80%;
  align-items: center;
}
.navbar2{
  display:flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  align-items: center;
}
.navbar1 a {
  display: block;
  text-decoration: none;
  color: white;
  padding: 4px 4px 4px 4px;
}
.navbar2 a {
  display: block;
  text-decoration: none;
  color: white;
  padding: 4px 12px 4px 4px;
}
.navbar2 a:hover {
  background-color: #C76A65;
  border-radius:50px;
  padding: 3px 8px 3px 8px;
  color: aliceblue;
}
.navbar1 a:hover {
  background-color: #C76A65;
  border-radius:50px;
  padding: 3px 8px 3px 8px;
  color: aliceblue;
}
ul {
  display:flex;
  justify-content: space-evenly;

}
li {
  display:flex;
   list-style-type: none;
}
@media screen and (max-width: 600px){
  .signupbase{
    width:95%;
  }
}
</style>
