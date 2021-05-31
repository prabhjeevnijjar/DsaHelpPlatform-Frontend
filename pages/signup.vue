<template>
  <div class="container">
    <div class="nav">
      <Nav />
    </div>
    <div class="signupbase">
      <div class="heading">
        <h1>Sign Up</h1>
        <a>Have an account? </a><NuxtLink to="/signin">Sign In</NuxtLink>
      </div>
      <hr>

      <div class="inputs">
        <a>First name</a>  <br>
        <input type="text"> <br>
        <a>Last Name</a> <br>
        <input type="text" name="" id=""> <br>
        <a>Email</a> <br>
        <input type="text" name="" id=""><br>
        <a>Password</a> <br>
        <input type="text" name="" id=""> <br>
        <a>Confirm Password</a> <br>
        <input type="text" name="" id=""> <br>
        <hr>
        <input class="button" type="button" value="Signup">
      </div>

      <div></div>

      <div></div>

      <div></div>

    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.signupbase{
  width: 50%;
  margin:  auto;
  border-style: solid;
  border-color: grey;
  border-width:0.5px;
  border-radius:10px;
  padding:30px;
}
.inputs input {
  padding:4px;
  margin:4px;
  margin-bottom: 8px;
  border-top: none;
  border-left:none;
  border-right:none;
  border-width:0.5px;
  width:100%;
  border-color: grey;
}
.inputs input:focus {
  outline:none;
}
.inputs a {
  font-size: 18px;
  color:grey;
}
.button {
  background: #C76A65;
  color: white;
  border-radius: 20px;
  letter-spacing: 1px;
  border:none;
}
.button:hover{
  -webkit-box-shadow: 1px 5px 15px -11px #000000; 
box-shadow: 1px 5px 15px -11px #000000;
}
</style>
