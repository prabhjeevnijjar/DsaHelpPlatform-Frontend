<template>
  <div class="container">
    <div class="nav">
      <Nav />
    </div>
    <div class="signupbase">
      <div class="heading">
        <h1>Recommend new resource</h1>
        <a>We will look at it and add it to our database! </a>
      </div>
      <hr>
      <div class="inputs">
        <form @submit.prevent="postSignupData">
          <a>Resource name</a> <br>
          <input v-model.lazy="resName" type="text" required><br>
          <a>Link to res</a> <br>
          <input v-model.lazy="link" type="text" required> <br>
          <hr>
          <input class="button" type="submit" value="Submit">
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
      link:"",
      resName:""
    }
  },
  methods:{
    async postSignupData() {
      const data = {
        link: this.link,
        description: this.resName
      }
     await this.$axios.$post('http://localhost:3001/homepage/recommend-resource', data)
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
