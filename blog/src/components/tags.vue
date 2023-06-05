<template >
    <div class="wrapper-grid--item right-side-bar">
                <h4 class="text-uppercase">Tags Cloud:</h4>

                <div class="tags-block">
                    <span @click="setTags(tag.name)" 
                        v-for="tag in tags" :key="tag" 
                        class="badge bg-primary"
                        :class='tag.color'
                        >
                    {{tag.name}}
                    </span>
                </div>

                <h4 class="text-uppercase">Authors:</h4>

                <div class="authors-block">
                    <div class="">
                        <span @click="setAuthors(author.name)"
                            v-for="author in authors" :key="author"
                            class="badge bg-secondary">
                        {{author.name}}
                        </span>
                    </div> 
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
            {name:"News", color:"blue"},
            {name:"Games",color:"green"},
            {name:"Ecology",color:"red"},
            {name:"Films",color:"orange"},
        ],
        authors:[
            {name:"By John Smith J"},
            {name:"By Alex Batareikin"},
            {name:"By Nadin Johnsons"},
            {name:"By Kriss Kriss"},
        ]
    }
  },
  methods:{
    setTags(tag){
        this.$emit('setTags',tag)
  },
    setAuthors(author){
        this.$emit('setAuthors',author)
  }
  }
  
}


</script>

<style scoped>

@import "../assets/styles/tags.scss";

.green {
    background: rgb(41, 202, 41);
}
.red{
    background: red;
}
.orange{
    background: orange;
}



</style>