<template>
<div class ="base">
  <div class="navbar1">
    <ul>
      <li><a href="http://">Helper</a></li>
    </ul>
  </div>
  <div class="navbar2">
    <ul>
      <li><a href="http://"><NuxtLink to="/">Homepage</NuxtLink></a></li>
      <li><a href="http://"><NuxtLink to="/signup">SignUp</NuxtLink></a></li>
      <li><a href="http://"><NuxtLink to="/login">Login</NuxtLink></a></li>
    </ul>
  </div>
</div>
</template>

<style>
.base{
  display:flex;
  justify-content: space-between;
  background-color: rgb(19, 246, 170);
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
  color: rgb(102, 102, 102);
  padding: 4px 4px 4px 4px;
}
.navbar2 a {
  display: block;
  text-decoration: none;
  color: rgb(102, 102, 102);
  padding: 4px 12px 4px 4px;
}
.navbar2 a:hover {
  background-color: rgb(0, 194, 129);
  border-radius:50px;
  padding: 3px 8px 3px 8px;
  color: aliceblue;
}
.navbar1 a:hover {
  background-color: rgb(0, 194, 129);
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
@media screen and (max-width: 600){
            /* .base{
                flex-direction: column;
            
            } */
  .navbar2{
    flex-direction: column;
  }
        }
</style>
