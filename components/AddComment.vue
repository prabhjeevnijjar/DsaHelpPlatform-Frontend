<template>
    <div class="root">
        <div class="showComments">
            
        </div>
        <div class="addComment">
            <div class="addComment_heading">
                <h5>Leave a review</h5>
            </div>
            <div class="addComment_input">
                <form >
                    <input type="text">
                    <button>Add</button>
                </form>
            </div>
        </div>
    </div>
</template>
<script>
    
</script>
<style scoped>
    .addComment_heading h5{
        color:grey;
        font-weight: 300;
        font-size: 12;
    }
    .addComment_input input{
        border-width: 0.5px;
        color:grey;
        border-radius:40px;
        padding: 2px 8px 2px 8px;
    }
    .addComment_input input:focus, textarea:focus, select:focus{
        outline: none;
    }
    .addComment_input button{
        border: none;
        border-color:grey;
        border-radius:40px;
        padding: 4px 10px 4px 10px;
    }
    .showComments{
        
    }
</style>