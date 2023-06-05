<template>
     <!--LEFT SIDE-BAR-->
    <div class="wrapper-grid--item left-side-bar">
        <div class="card">
            <h4 class="card-header text-uppercase">All posts:</h4>

            <div v-if="tegName || authorName"  class="filter-current bg-dark text-white"> Filter by:
                <span> s</span>
                <button class="filter-current bg-dark text-white d-none" type="button" uk-close></button>
            </div>

            <ul class="list-group">
                <li 
                    v-for="item in articles" :key="item.article"  
                    @click="selectArticle(item.article)" 
                    class="list-group-item item--active" >
                        <a  class="d-block text-decoration-none text-black" href="#">Article - {{ item.article }} </a>
                </li>
            </ul>
        </div> 
    </div>
        <!--/LEFT SIDE-BAR-->
</template>

<script>
export default {
  name: 'sidebar-articles',
  props: ['tegName', 'authorName'],

  
data(){
    return {
        showTagAuthor: [
        { 
            article:1, 
            tags:["News","Games"],
            author:"By John Smith J"
        },
        { 
            article:2,
            tags:"Ecology",
            author:"By Nadin Johnsons"
        },
        {
            article:3, 
            tags:["Ecology","Films"],
            author:"By Nadin Johnsons"
        },
        { 
            article:4, 
            tags:["Games", "Games"],
            author:"By Kriss Kriss" 
        },
        { 
            article:5, 
            tags:"News",
            author:"By Alex Batareikin"  
        },
        { 
            article:6, 
            tags:["Ecology","News"],
            author:"By Nadin Johnsons" 
        },
        { 
            article:7,
            tags:"News",
            author:"By Alex Batareikin"
        },
        { 
            article:8, 
            tags:"Games",
            author:"By John Smith J"
        },
        { 
            article:9, 
            tags:["News","Games"],
            author:"By Alex Batareikin" 
        },
        { 
            article:10,
            tags:"Ecology",
            author:"By Kriss Kriss"
        },
        { 
            article:11,
            tags:"Films",
            author:"By Nadin Johnsons"
        }
    ]
    }
},
computed: {
    articles() {
        if(this.tegName) {
            const arr = this.showTagAuthor.filter(item => item.tags.includes(this.tegName) || item.tags == this.tegName)
            console.log('res', arr)
            return arr
        } else if(this.authorName) {
            console.log(this.authorName)
            const arr2 = this.showTagAuthor.filter(item => item.author == this.authorName)
            console.log('res', arr2)
            return arr2
        } else return this.showTagAuthor
    }
},
methods: {
    selectArticle(number) {
        this.$emit('setArticle', number)
    }
},



}

</script>

<style scoped>
@import "../assets/styles/sidebar.scss";


</style>
