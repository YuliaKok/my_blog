<template>
     <!--LEFT SIDE-BAR-->
    <div class="wrapper-grid--item left-side-bar">
        <div class="card">
            <h4 class="card-header text-uppercase">All posts:</h4>

            <div v-if="selectedFilter"  class="filter-current bg-dark text-white "> Filter by:
                  <span>{{ selectedFilter }}</span>
                  <button class="ilter-current bg-dark text-white" v-on:click="remove">X</button>
            
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
        ],
        selectedFilter: null
    }
},
    computed: {
        articles() {
            if(this.tegName && this.selectedFilter) {
                const arr = this.showTagAuthor.filter(item => item.tags.includes(this.tegName) || item.tags == this.tegName)
                return arr
            } else if(this.authorName && this.selectedFilter) {
                const arr2 = this.showTagAuthor.filter(item => item.author == this.authorName)
                return arr2
            } else return this.showTagAuthor
        },
    },
    methods: {
        selectArticle(number) {
           this.$emit('setArticle', number)
        },
        remove(){
            this.selectedFilter = null
        }
    },
        
    watch: {
        tegName(value) {
            if(value) this.selectedFilter = value
        },

        authorName(value) {
            if(value) this.selectedFilter = value
        }
    }
       
}

</script>

<style scoped>
@import "../assets/styles/sidebar.scss";


</style>
