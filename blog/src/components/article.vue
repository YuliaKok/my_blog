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
                            <span class="badge bg-secondary">By John Smith J</span> <span class="author--cnt badge bg-secondary"></span>
                        </p>
                        <a href="#" class="btn text-uppercase">read more</a>
                    </div>
                    <div class="card-footer text-muted">
                        <div class="card-footer-grid">
                            <div class="">Tags:</div>
                            <div class="text-end">
                                <span class="badge bg-primary">News</span>
                                <span class="badge bg-success">Games</span>
                            </div>
                        </div>
                    </div>
                </div> <!--/.card-->
                </div>
</template>

<script>
export default {
  name: 'article-item',
  props: {
    msg: String,
    articleNumber: Number
  },

  data() {
    return {
        showImg: [
   { article:1, imgSrc: "../assets/img/photo-1.jpg" },
   { article:2, imgSrc:"../assets/img/photo-2.jpg" },
   { article:3, imgSrc:"../assets/img/photo-3.jpg" },
   { article:4, imgSrc:"../assets/img/photo-4.jpg" },
   { article:5, imgSrc:"../assets/img/photo-5.jpg" },
   { article:6, imgSrc:"../assets/img/photo-6.jpg"},
   { article:7, imgSrc:"../assets/img/photo-7.jpg"},
   { article:8,  imgSrc:"../assets/img/photo-8.jpg"},
   { article:9, imgSrc:"../assets/img/photo-9.jpg" },
   { article:10, imgSrc:"../assets/img/photo-10.jpg"},
   { article:11, imgSrc:"../assets/img/photo-11.jpg"},
        ]
    }
  },
  methods:{
    getImg(){ 
        if(this.articleNumber) return require(`@/assets/img/photo-${this.articleNumber}.jpg`)
        else return require(`@/assets/img/photo-1.jpg`)
    },

  },
  
     
  }
  


</script>

<style scoped>
@import "../assets/styles/sidebar.scss";

</style>