<template>
<div class="rootclass">{{this.title}}
    <div class="contentcard"> 
          
          <div class="contentcard_title">
            <a :href="this.link">{{this.name}}</a>
          </div>      <hr>
          <div class="contentcard_socials">
            <div class="contentcard_socials_like">
              <button>Upvotes</button>
              <a>{{this.upvoteCount}}</a>
            </div>
            <div class="contentcard_socials_dislike">
              <button>Downvotes</button>
              <a>{{this.downVoteCount}}</a>
            </div>
            <div class="contentcard_socials_comment">             
               <img src="/comment.png" alt="comment section">
               <a>{{this.commentCount}}</a>
            </div>
            <div class="contentcard_socials_bookmark">
              <button type="submit">Save</button>
            </div>
          </div>
          <br>
      </div>
    </div>
</template>
<script>
export default {
      props: ['link','name','commentCount','upvoteCount','downVoteCount'],
      data: function() {
          return {
              link: this.link,
              name: this.name,
              commentCount: this.commentCount,
              upvoteCount: this.upvoteCount,
              downVoteCount: this.downVoteCount
          }
      }

}
</script>
<style scoped>
.contentcard {
  margin: 4px 20px 10px 8px;
  padding: 6px 10px 0px 8px;
  border-style: solid;
  border-width: 0.25px;
  border-radius: 8px;
  border-color: rgb(173, 172, 172);
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