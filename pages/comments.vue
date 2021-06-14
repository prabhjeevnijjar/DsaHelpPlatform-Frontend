<template>
<div class="rootclass">
  <div class="nav">
      <Nav />
  </div>
  <div class="search">
    <Searchbar />
  </div>
  <div class="datacontainer">
    <div class="leftcolumn">
      <div class="header">
        <div class="logo">
          <img src="/comment.png" alt="comment section">
        </div>
        <div class="heading">
          <h2>Discussion...</h2>
        </div>
      </div>
        <div class="contentcards">
        <StaticContentCard 
        :commentId="$route.query.commentId"
        :link="$route.query.link" 
        :name="$route.query.name"
        :commentCount="$route.query.commentCount"
        :upvoteCount="$route.query.upvoteCount"
        :downVoteCount="$route.query.downVoteCount"
        />
      </div>
      <div class="discussion">
        <div class="discussion_addnew">
          <h4>Add to the discussion</h4>
          <textarea type="text"></textarea>
        </div>
        <div>
          <h4></h4>
        </div>
        <div class="discussion_comments_enclosure">
          <div v-for="item in serverResponse.data" :key="item.postedDate" class="discussion_comment_box">
            <div><p>{{item.commentText}}</p></div>
          </div>
        </div>
      </div>
    </div>
    <div class="rightcolumn">
      <h2>Featured</h2> 
      <h2>What's new</h2>
      <h2>Recommended</h2>
    </div>
  </div>
</div>
</template>
<script>
export default {
  props: {
    link: {
      type: String,
      required: false,
    },
    name: {
      type: String,
      required: false,
    },
    commentCount: {
      type: Number,
      required: false,
    },
    upvoteCount: {
      type: Number,
      required: false,
    },
    downVoteCount: {
      type: Number,
      required: false,
    },
    commentId:{
      type:String,
      required:false
    }
  },
  created() {
    // console.log("datdadtatad",this.resourceID.typeOf())
       this.$axios.$get('http://localhost:3001/homepage/comment',
        {
          params: {
            resourceId:this.resourceID
          }
        }) //this commentId is actuallly the resource id whos commetns are being fetched
      .then((serverResponse)=>{
        this.serverResponse = serverResponse;
        console.log("res data: ",serverResponse);
      })
      .catch((error)=>{
        console.log("error: ",error);
      }) 
  },
  data:function(){
    return{
     serverResponse: {},
     resourceID: this.$route.query.commentId
    }
  }
}
</script>
<style scoped>
.header{
  display: flex;
  flex-wrap:wrap;
  justify-content:start;
}
.logo img{
  width: 45px;
  margin-right: 10px;
}
.discussion{
  margin: 4px 20px 10px 8px;
}
.discussion_addnew textarea{
  width:90%;
}

.discussion_addnew textarea{
  width:100%;
  display: block;
  border-radius: 6px;
  border-width: 0.25px;
  border-color: rgb(185, 185, 185);
  padding: 3px 3px 3px 9px;
}
.discussion_addnew textarea:focus, textarea:focus, select:focus{
  outline: none;
}
.discussion_comments_enclosure{
  overflow: auto;
  height: 350px;
  width: 100%;
  border-style: solid;
  border-width: 0.25px;
  padding: 15px;
  border-color: rgb(214, 214, 214);
  margin-top:25px;
  border-radius: 8px;

}
.discussion_comment_box{
  border-style: solid;
  width:100%;
  padding: 10px 15px 10px 15px;
  border-color: rgb(214, 214, 214);
    border-width: 0.25px;

  margin-top: 10px;
  border-radius: 8px;
}
</style>