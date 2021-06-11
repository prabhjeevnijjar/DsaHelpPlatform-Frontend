<template>
<div 
  components: { Searchbar },
  class="basecontainer">
  <div class="nav">
      <Nav />
  </div>
  <div class="search">
    <Searchbar />
  </div>
  <div class="datacontainer">
    <div class="leftcolumn">
      <h2>Posts</h2> 
      <!-- inject data from API in here -->
      <div class="contentcards">
        <Contentcard />
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

</style>
