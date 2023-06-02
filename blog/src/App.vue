<template>

  <div class="containers">
    <sidebar @setArticle="setArticle" />
    <articleItem :articleNumber="articleNumber" />
    <tagsItem />
  </div>
</template>

<script>

import sidebar from './components/sidebar.vue';
import articleItem from './components/article.vue';
import tagsItem from './components/tags.vue';


export default {
  components: {sidebar, articleItem, tagsItem},

  data() {
    return {
      articleNumber: null
    }
  },
  methods: {
    setArticle(articleNumber) {
      console.log('event', articleNumber)
      this.articleNumber = articleNumber
      
    

    }
  }


}



</script>

<style>
@import "../src/assets/styles/index.scss";

.containers{
  display: grid;
  max-width: 1320px;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 1rem 1rem;

  margin: 0 auto;
  margin-top: 35px;
}
</style>
