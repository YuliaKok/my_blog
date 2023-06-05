<template>

  <div class="containers">

    <sidebar @setArticle="setArticle" :tegName="tegName" :authorName="authorName"/>
    <articleItem :articleNumber="articleNumber" :tegName="tegName" :authorName="authorName" />
    <tagsItem @setTags="giveTags" @setAuthors="giveAuthors" />

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
      articleNumber: null,
      tegName:null,
      authorName:null,
      
    }
  },
  methods: {
    setArticle(articleNumber) {
      console.log('event', articleNumber)
      this.articleNumber = articleNumber
      },
    giveTags(nameTag){
        this.tegName = nameTag
        console.log('child component said tags', nameTag)
    },
    giveAuthors(nameAuthor){
      this.authorName = nameAuthor
      console.log('child component said tags', nameAuthor)
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
