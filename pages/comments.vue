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
          <h1>Discussion...</h1>
        </div>
      </div>
        <div class="contentcards">
        <StaticContentCard 
        :link="$route.query.link" 
        :name="$route.query.name"
        :commentCount="$route.query.commentCount"
        :upvoteCount="$route.query.upvoteCount"
        :downVoteCount="$route.query.downVoteCount"
        />
      </div> 
      <div class="discussion">
        <div class="discussion_addnew">
          <h4>Write your review here</h4>
          <textarea type="text"></textarea>
        </div>
        <div class="discussion_showall">

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
    }
  },
  data:function(){
    return{
     
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
  width: 80px;
}
.discussion{
  margin: 4px 20px 10px 8px;
}
.discussion_addnew textarea{
  width:90%;
}

.discussion_addnew textarea{
  width:90%;
  display: block;
  border-radius: 6px;
  border-width: 0.25px;
  padding: 3px 3px 3px 9px;
}
.discussion_addnew textarea:focus, textarea:focus, select:focus{
  outline: none;
}
</style>