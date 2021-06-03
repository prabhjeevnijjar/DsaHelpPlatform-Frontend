<template>
<div class="basecontainer">
  <div class="nav">
      <Nav />
  </div>
  <div class="searchbar">
    <input type="text" placeholder="Search">
  </div>
  <div class="datacontainer">
    <div class="leftcolumn">
      <h2>Posts</h2> 
      
      <!-- inject data from API in here -->
      <div class="contentcard"> 
          <div class="contentcard_title">
            <a href="https://www.geeksforgeeks.org/program-and-syntax-for-iscntrlint-c-function-in-c/">Program and syntax for iscntrlint c function in c</a>
          </div>
          <div class="contentcard_source">
            <a href="https://www.geeksforgeeks.org/">geeksforgeeks</a>
          </div>
          <div class="contentcard_tags">
            #linkedlist #array #backtracking
          </div>        
          <div class="contentcard_socials">
            <div class="contentcard_socials_like">
              <a>Upvote</a>
              <a>120</a>
            </div>
            <div class="contentcard_socials_dislike">
              <a>Downvote</a>
              <a>5</a>
            </div>
            <div class="contentcard_socials_bookmark">
              <input type="button" value="save">
            </div>
          </div>
          <hr>
      </div>
      <div class="discussion">

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

</script>

<style>

.datacontainer{
  left:20;
  right:20px;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  padding:40px 10px 0px;
}
.leftcolumn{
  display: flex;
  flex-wrap:wrap;
  flex-direction: column;
  flex-basis: 60%;
}
.leftcolumn h1{
  margin: auto;
}
.rightcolumn{
  display: flex;
  flex-wrap:wrap;
  flex-direction: column;
  flex-basis: 40%;
}
.searchbar {
  align-content: center;
  padding:8px; 
}
.searchbar input{
  width:60%;
  display: block;
  margin:0 auto; 
  border-radius: 12px;
  border-width: 0.25px;
  padding: 3px 3px 3px 9px;
}
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
