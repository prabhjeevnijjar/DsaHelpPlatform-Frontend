<template>
  <div class="container">
    <div class="nav">
      <Nav />
    </div>
    <div class="signupbase">
      <div class="heading">
        <h1>Login</h1>
        <a>Don't have an account? </a><NuxtLink to="/signup">Sign up</NuxtLink>
      </div>
      <hr>
      <div class="inputs">
        <form @submit.prevent="postSignupData">
          <a>Email</a> <br>
          <input v-model.lazy="email" type="text" required><br>
          <a>Password</a> <br>
          <input v-model.lazy="password" type="text" required> <br>
          <hr>
          <input class="button" type="submit" value="Login">
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
      email:"",
      password:"",
    }
  },
  methods:{
    async postSignupData() {
    const data = {
      email: this.email,
      password: this.password,
    }
    console.log(data);
     await this.$axios.$post('http://localhost:3001/api/login', data)
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
