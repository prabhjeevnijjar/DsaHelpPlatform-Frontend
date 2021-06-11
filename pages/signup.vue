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
        <form @submit.prevent="postSignupData">
          <a>First name</a>  <br>
          <input v-model.lazy="fname" type="text" required > <br>
          <a>Last Name</a> <br>
          <input v-model.lazy="lname" type="text" required> <br>
          <a>Email</a> <br>
          <input v-model.lazy="email" lname type="text" required><br>
          <a>Password</a> <br>
          <input v-model.lazy="password" type="text" required> <br>
          <a>Confirm password</a> <br>
          <input v-model.lazy="cpassword" type="text" required> <br>
          <hr>
          <input  class="button" type="submit" value="Signup">
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      serverResponse :{},
      fname:"",
      lname:"",
      email:"",
      password:"",
      cpassword:"",
      
    }
  },
  methods:{
    async postSignupData() {
       const data = {
        FirstName: this.fname,
          LastName: this.lname,
          Email: this.email,
          Password: this.password,
    }
     await this.$axios.$post('http://localhost:3001/api/register', data)
      .then((serverResponse)=>{
        this.serverResponse = serverResponse;
        console.log("res data: ",serverResponse);
      })
      .catch((error)=>{
        console.log("error: ",error);
      }) 
  }
  }
}
</script>


<style scoped>
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
@media screen and (max-width: 844px){
  .signupbase {
    width:none;
  }
}
</style>
