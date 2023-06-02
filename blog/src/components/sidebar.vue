<template>
     <!--LEFT SIDE-BAR-->
    <div class="wrapper-grid--item left-side-bar">
        <div class="card">
            <h4 class="card-header text-uppercase">All posts:</h4>
            <div class="filter-current bg-dark text-white d-none">Filter by: &nbsp;<code></code> <b>X</b></div>
            <ul class="list-group">
                <li 
                    v-for="item in showTagAuthor" :key="item.article"  
                    @click="selectArticle(item.article)" 
                    class="list-group-item item--active" >
                        <a  class="d-block text-decoration-none text-black" href="#">Article - {{ item.article }}</a>
                </li>
            </ul>
        </div> 
    </div>
        <!--/LEFT SIDE-BAR-->
</template>

<script>
export default {
  name: 'sidebar-articles',
  props: {
    msg: String
  },
data(){
    return {
        showTagAuthor: [
        { 
            article:1, 
            tags:["News","Games"],
            author:"John Smith J"
        },
        { 
            article:2,
            tags:"Ecology",
            author:"Nadin Johnsons"
        },
        {
            article:3, 
            tags:["Ecology","Films"],
            author:"Nadin Johnsons"
        },
        { 
            article:4, 
            tags:["Games", "Games"],
            author:"Kriss Kriss" 
        },
        { 
            article:5, 
            tags:"News",
            author:"Alex Batareikin"  
        },
        { 
            article:6, 
            tags:["Ecology","News"],
            author:"Nadin Johnsons" 
        },
        { 
            article:7,
            tags:"News",
            author:"Alex Batareikin"
        },
        { 
            article:8, 
            tags:"Games",
            author:"John Smith J"
        },
        { 
            article:9, 
            tags:["News","Games"],
            author:"Alex Batareikin" 
        },
        { 
            article:10,
            tags:"Ecology",
            author:"Kriss Kriss"
        },
        { 
            article:11,
            tags:"Films",
            author:"Nadin Johnsons"
        }
    ]
    }
},
methods: {
    selectArticle(number) {
        this.$emit('setArticle', number)
    }
}
}

</script>

<style scoped>
@import "../assets/styles/sidebar.scss";


</style>
