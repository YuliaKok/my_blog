<template >
    <div class="wrapper-grid--item right-side-bar">
                <h4 class="text-uppercase">Tags Cloud:</h4>
                <div class="tags-block">
                    <span class="badge bg-primary" data-tags="news"> <a href="#" class="text-white text-decoration-none">News</a> </span>
                    <span class="badge bg-success" data-tags="games"> <a href="#" class="text-white text-decoration-none">Games</a> </span>
                    <span class="badge bg-danger" data-tags="ecology"> <a href="#" class="text-white text-decoration-none">Ecology</a> </span>
                    <span class="badge bg-warning" data-tags="films"> <a href="#" class="text-white text-decoration-none">Films</a> </span>
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
  display:grid; grid-template-columns:1fr 1fr 1fr; grid-gap:1rem 1rem;
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
  outline:1px solid black; 
  padding:10px;
}

.left-side-bar .filter-current{ 
    position:relative; 
    padding:4px 6px; 
}
.left-side-bar .filter-current b{
     position:absolute;
      right:5px; 
      cursor:pointer; 
      }
.left-side-bar .card ul.list-group li.list-group-item.item--active { 
    background-color: #ffc107; 
    }

.central-content .card{
    display:none;
    }
.central-content .card.card--active{ 
    display:block; 
    }
.central-content .card .card-footer .card-footer-grid{
     display:grid; 
     grid-template-columns:1fr 1fr; 
     justify-items:stretch; }

</style>