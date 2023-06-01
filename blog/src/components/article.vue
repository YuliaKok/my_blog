<template>
    <div class="wrapper-grid--item central-content">
                <div class="card card--active" data-id="1" data-tags="news games" data-author="John Smith J">
                    <div class="card-body text-center">
                        <h5 class="card-title text-capitalize">Article Title - {{articleNumber}}</h5>
                        <img :src="getImg()" alt="Card image cap">
                        <p class="card-text fst-italic">
                            Article Title - 1: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet volutpat consequat mauris nunc congue nisi. Mi sit amet mauris commodo. Massa sed elementum tempus egestas sed. Dignissim sodales ut eu sem integer. <br><br>Ipsum consequat nisl vel pretium. Nunc vel risus commodo viverra maecenas accumsan. Aliquam etiam erat velit scelerisque in dictum non consectetur a. Imperdiet dui accumsan sit amet. Nibh nisl condimentum id venenatis a condimentum vitae. Est ultricies integer quis auctor elit sed vulputate.
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
   { article:1, imgSrc: "../assets/photo-1.jpg" },
   { article:2, imgSrc:"../assets/photo-2.jpg" },
   { article:3, imgSrc:"../assets/photo-3.jpg" },
   { article:4, imgSrc:"../assets/photo-4.jpg" },
   { article:5, imgSrc:"../assets/photo-5.jpg" },
   { article:6, imgSrc:"../assets/photo-6.jpg"},
   { article:7, imgSrc:"../assets/photo-7.jpg"},
   { article:8,  imgSrc:"../assets/photo-8.jpg"},
   { article:9, imgSrc:"../assets/photo-9.jpg" },
   { article:10, imgSrc:"../assets/photo-10.jpg"},
   { article:11, imgSrc:"../assets/photo-11.jpg"},
        ]
    }
  },
  methods:{
    getImg(){ 
        const article = this.showImg.filter(i => i.article == this.articleNumber)

        if(article)  {
            console.log('art', article[0], article[0]?.imgSrc)
            return article[0]?.imgSrc
        }
        else return ''
    }
  }
} 



</script>

<style scoped>
body{
    margin:0;
     padding:0; 
     font-family:Ubuntu,sans-serif; 
     font-size:1rem; 
     }

.container{ 
    max-width:1320px;
    margin:0 auto; 
    }

.wrapper-grid{
  margin-top:35px;
  display:grid; 
  grid-template-columns:1fr 1fr 1fr;
  grid-gap:1rem 1rem;
}

.text-center{ 
    text-align:center !important; 
    }  

.text-end{ 
    text-align:end !important;  
    }
.text-uppercase { 
    text-transform:uppercase;
     }
.text-capitalize {
     text-transform:capitalize; 
     }
.fst-italic{ 
    font-style:italic; 
    }
.text-decoration-none{ 
    text-decoration:none !important; 
    }

.d-none{ 
    display:none !important; 
    }
.d-block{ 
    display:block !important; 
    }

.text-black{ 
    color:#000000; 
    }
.text-white{ 
    color:#ffffff; 
    }
.text-muted{ 
    color:#777777; 
    }
.bg-secondary{ 
    background-color:rgb(108,117,125); 
    }
.bg-primary{ 
    background-color:rgb(13,110,253); 
    }
.bg-success{ 
    background-color:rgb(25,135,84); 
    }
.bg-danger{ 
    background-color:rgb(220,53,69); 
    }
.bg-warning{ 
    background-color:rgb(255,193,7); 
    }
.bg-dark{
    background-color:rgb(33,37,41); 
    }

.badge {
  display:inline-block; 
  padding:0.35em 0.65em; 
  font-size:.75em; 
  font-weight:700;
  line-height:1; 
  color:#fff; 
  text-align:center; 
  white-space:nowrap; 
  vertical-align:baseline; 
  border-radius:0.25rem;
}
code {
     font-size:.875em;
     color:#d63384; 
     word-wrap:break-word; 
     }
.list-group{ 
    padding-left:0; 
    margin-bottom:0; 
    border-radius:0.25rem; 
    }
.list-group-item { 
    position:relative; 
    display:block; 
    padding:0.5rem 1rem; 
    margin:4px 0; 
    color:#212529; 
    text-decoration:none; 
    background-color:#fff;
     border:1px solid rgba(0,0,0,.125); 
     }
/*____________________________________/MAIN*/


.wrapper-grid--item{
  outline:1px solid black; padding:10px;
}

.left-side-bar .filter-current{ position:relative; padding:4px 6px; }
.left-side-bar .filter-current b{ position:absolute; right:5px; cursor:pointer; }
.left-side-bar .card ul.list-group li.list-group-item.item--active { background-color: #ffc107; }

.central-content .card{ display:none; }
.central-content .card.card--active{ display:block; }
.central-content .card .card-footer .card-footer-grid{ display:grid; grid-template-columns:1fr 1fr; justify-items:stretch; }


.wrapper-grid--item {
    text-align: center;
}
</style>