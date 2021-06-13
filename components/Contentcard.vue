<template>
<div class="rootclass">
    <div v-for="item in serverResponse.data" :key="item.postedDate" class="contentcard"> 
          <div class="contentcard_title">
            <a :href="item.resourcelink">{{item.name}}</a>
          </div>
          
          <div class="contentcard_tags">
            #{{item.resourcetype}} 
          </div>        
          <div class="contentcard_socials">
            <div class="contentcard_socials_like">
              <button v-on:click="upVote(item._id)" type="submit">Upvote</button>
              <a>{{item.upvotecount}}</a>
            </div>
            <div class="contentcard_socials_dislike">
              <button v-on:click="downVote(item._id)" type="submit">Downvote</button>
              <a>{{item.downvotecount}}</a>
            </div>
            <div class="contentcard_socials_comment">
              <NuxtLink to="/comments"><img src="/comment.png" alt="comment section"></NuxtLink>
              <a>{{item.commentcount}}</a>
            </div>
            <div class="contentcard_socials_bookmark">
              <button type="submit">Save</button>
            </div>
          </div>
          <br>
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
      async upVote(postId) {
       console.log(postId);
        await this.$axios.$put('http://localhost:3001/homepage/up-vote',{body:{"null":"null"}},{ params: {adId: postId }})
          .then((serverResponse)=>{
            this.serverResponse = serverResponse;
            console.log("res data: ",serverResponse);
          })
          .catch((error)=>{
            console.log("error: ",error);
          }) 
      },
      async downVote(postId) {
        console.log(postId);
        this.$axios.$put('http://localhost:3001/homepage/down-vote',{body:{"null":"null"}},{ params: { adId: postId } })
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
.contentcard {
  margin: 4px 20px 10px 8px;
  padding: 6px 10px 0px 10px;
  /* border-style: solid;
  border-width: 0.25px;
  border-radius: 4px;
  border-right:none;
  border-left: none;
  border-color: grey; */
}
.contentcard_title{
  font-size: 24px;
  text-align: center;
}
.contentcard_tags{
  font-size:16px;
  text-align: center;
  color:grey;
  margin: auto;
}
.contentcard_socials{
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: space-evenly;
}

.contentcard_socials_like{
  margin-right:5px;
}
.contentcard_socials_dislike{
  margin-right:5px;
}
.contentcard_socials_like button {
    border: none;
    background-color: pink;
    border-radius: 6px;
}
.contentcard_socials_dislike button {
  border: none;
  background-color: rgb(252, 209, 216);
  border-radius: 6px;
}
.contentcard_socials_bookmark button {
  border: none;
  background-color: #50a5fa;
  color: aliceblue;
  border-radius: 6px;
}
.contentcard_socials_bookmark{
  margin-right:5px;
}
.contentcard_socials_comment img{
  width:28px;
}
.contentcard_socials_comment:hover{
cursor: pointer;
}
</style>