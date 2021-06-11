<template>
<div class="rootclass">
    <div v-for="item in serverResponse.data" :key="item.postedDate" class="contentcard"> 
          <div class="contentcard_title">
            <a>{{item.name}}</a>
          </div>
          <div class="contentcard_source">
            <a :href="item.resourcelink">click here to access</a>
          </div>
          <div class="contentcard_tags">
            #{{item.resourcetype}} #{{item.resourcesubtype["item"]}} 
          </div>        
          <div class="contentcard_socials">
            <div class="contentcard_socials_like">
              <a>Upvote</a>
              <a>{{item.upvotecount}}</a>
            </div>
            <div class="contentcard_socials_dislike">
              <a>Downvote</a>
              <a>{{item.downvotecount}}</a>
            </div>
            <div class="contentcard_socials_bookmark">
              <input type="button" value="save">
            </div>
            <div>{{serverResponse.data["0"]}}</div>
          </div>
          <hr>
      </div>
    </div>
</template>
<script>
export default {
  data: function() {
    return {
      serverResponse :{}
      }
  },
  created() {
      this.$axios.$get('http://localhost:3001/homepage/resource')
      .then((serverResponse)=>{
        this.serverResponse = serverResponse;
        console.log("res data: ",serverResponse);
      })
      .catch((error)=>{
        console.log("error: ",error);
      }) 
  },
  methods: {
      async upVote()
  }
}
</script>
<style scoped>
.contentcard {
  margin: 4px 20px 10px 8px;
  padding: 6px 6px 6px 6px;
  /* border-style: solid;
  border-width: 0.25px;
  border-radius: 4px;
  border-right:none;
  border-left: none;
  border-color: grey; */
}
.contentcard_title{
  font-size: 22px;
}
.contentcard_tags{
  font-size:16px;
  color:grey;
}
.contentcard_socials{
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: end;
}
.arrow-up {
  width: 0; 
  height: 0; 
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-bottom: 10px solid grey;
}
.arrow-down{
  width: 0; 
  height: 0; 
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-top: 10px solid grey;
}
.contentcard_socials_like{
  margin-right:5px;
}
.contentcard_socials_dislike{
  margin-right:5px;
}
.contentcard_socials_bookmark{
  margin-right:5px;
}
</style>