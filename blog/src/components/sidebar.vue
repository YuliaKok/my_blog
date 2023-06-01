<template>
     <!--LEFT SIDE-BAR-->
    <div class="wrapper-grid--item left-side-bar">
        <div class="card">
            <h4 class="card-header text-uppercase">All posts:</h4>
            <div class="filter-current bg-dark text-white d-none">Filter by: &nbsp;<code></code> <b>X</b></div>
            <ul class="list-group">
                <li @click="$emit('setArticle', item)" v-for="item in 11" :key="item" class="list-group-item item--active" data-id="1" data-tags="news games" data-author="John Smith J">
                    <a  class="d-block text-decoration-none text-black" href="#">Article - {{ item }}</a>
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
  data() {
    return {
        items: [1,2,3]
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

</style>
