<template >
    <div class="wrapper-grid--item right-side-bar">
                <h4 class="text-uppercase">Tags Cloud:</h4>
                <div class="tags-block">
                    <span 
                        v-for="tag in tags" :key="tag" 
                        class="badge bg-primary"
                        :style="{`` backgroundColor: ${tag.color}`}"
                        >
                        <a href="#" class="text-white text-decoration-none">{{tag.name}}</a> 
                    </span>
                </div>

                <h4 class="text-uppercase">Authors:</h4>
                <div class="authors-block">
                    <div class="">
                        <span class="badge bg-secondary" data-author="John Smith J"> <a href="#" class="text-white text-decoration-none">By John Smith J</a> </span>
                        <span class="badge bg-secondary" data-author="Alex Batareikin"> <a href="#" class="text-white text-decoration-none">By Alex Batareikin</a> </span>
                        <span class="badge bg-secondary" data-author="Nadin Johnsons"> <a href="#" class="text-white text-decoration-none">By Nadin Johnsons</a> </span>
                        <span class="badge bg-secondary" data-author="Kriss Kriss"> <a href="#" class="text-white text-decoration-none">By Kriss Kriss</a> </span>
                    </div> <!--/.row-->
                </div>
            </div>
            
    
</template>

<script>
export default {
  name: 'tags-item',
  props: {
    msg: String
  },
  data(){
    return{
        tags:[
            {name:"News", color:"green"},
            {name:"Games",color:"yellow"},
            {name:"Ecology",color:"blue"},
            {name:"Films",color:"red"},
            

        ]
    }
  }
  
}


</script>

<style scoped>
@import "../assets/styles/tags.scss";
.green {
    background: rgb(41, 202, 41);
}

</style>