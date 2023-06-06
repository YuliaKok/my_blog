<template>
    <div class="wrapper-grid--item central-content">
                <div class="card card--active" data-id="1" data-tags="news games" data-author="John Smith J">
                    <div class="card-body text-center">
                        <h5 class="card-title text-capitalize">Article Title - {{articleNumber}}</h5>
                        <img :src="getImg()" alt="Card image cap">
                        <p class="card-text fst-italic">
                           <span>Article Title - {{articleNumber}}: </span> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet volutpat consequat mauris nunc congue nisi. Mi sit amet mauris commodo. Massa sed elementum tempus egestas sed. Dignissim sodales ut eu sem integer. <br><br>Ipsum consequat nisl vel pretium. Nunc vel risus commodo viverra maecenas accumsan. Aliquam etiam erat velit scelerisque in dictum non consectetur a. Imperdiet dui accumsan sit amet. Nibh nisl condimentum id venenatis a condimentum vitae. Est ultricies integer quis auctor elit sed vulputate.
                        </p>
                        <p class="card-author text-end">
                            <span class="badge bg-secondary">{{getAuthorName()}}</span>
                            <span class="author--cnt badge bg-secondary"> {{ articlesQtty }} </span>
                        </p>
                        <a href="#" class="btn text-uppercase">read more</a>
                    </div>
                    <div class="card-footer text-muted">
                        <div class="card-footer-grid">
                            <div class="">Tags:</div>
                            <div class="text-end">
                                <span class="badge bg-primary">{{getTagsName()}}</span>
                            </div>
                        </div>
                    </div>
                </div> <!--/.card-->
                </div>
</template>

<script>
export default {
  name: 'article-item',
  props: ['articleNumber','tegName', 'authorName'],

  data() {
    return {

        showImg: [
   { article:1, imgSrc: "../assets/img/photo-1.jpg", tags:["News","Games"], author:"By John Smith J" },
   { article:2, imgSrc:"../assets/img/photo-2.jpg",tags:"Ecology",author:"By Nadin Johnsons" },
   { article:3, imgSrc:"../assets/img/photo-3.jpg",tags:["Ecology","Films"], author:"By Nadin Johnsons" },
   { article:4, imgSrc:"../assets/img/photo-4.jpg",tags:"Games",author:"By Kriss Kriss" },
   { article:5, imgSrc:"../assets/img/photo-5.jpg",tags:"News",author:"By Alex Batareikin" },
   { article:6, imgSrc:"../assets/img/photo-6.jpg",tags:["Ecology","News"],author:"By Nadin Johnsons"},
   { article:7, imgSrc:"../assets/img/photo-7.jpg", tags:"News",author:"By Alex Batareikin"},
   { article:8,  imgSrc:"../assets/img/photo-8.jpg",tags:"Games",author:"By John Smith J"},
   { article:9, imgSrc:"../assets/img/photo-9.jpg", tags:["News","Games"],author:"By Alex Batareikin" },
   { article:10, imgSrc:"../assets/img/photo-10.jpg", tags:"Ecology",author:"By Kriss Kriss"},
   { article:11, imgSrc:"../assets/img/photo-11.jpg",tags:"Films",author:"By Nadin Johnsons"}]
    }
  },
  computed: {
    articlesQtty() {
        // console.log('name', this.authorName)
        const result = this.showImg.filter(el => el.author == this.authorName)
        console.log('res', result, result.length)
        return result.length
    }
  },
  methods:{
    getImg(){ 
        if(this.articleNumber) return require(`@/assets/img/photo-${this.articleNumber}.jpg`)
        else return require(`@/assets/img/photo-1.jpg`)
    },
    getTagsName(){
        let articleNum;
        this.articleNumber ? articleNum = this.articleNumber : articleNum = 1

        const article = this.showImg.filter(item => item.article == articleNum)[0]
        if(article) {
            let res = article.tags
            res = res.toString()
            return res
        } 
    },
    getAuthorName(){
        let articleNumb;
        this.articleNumber ? articleNumb = this.articleNumber : articleNumb = 1

        const article = this.showImg.filter(item => item.article == articleNumb)[0]
        if(article) {
            let res = (article.author)
            return res
        }
    },
    // getNumber(){
    //     const result = this.showImg.filter((el) => {el.author == this.authorName})

    //     return result.length
    // }

  }
     
  }
  


</script>

<style scoped>
@import "../assets/styles/sidebar.scss";

</style>