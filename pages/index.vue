<template>
  <div class="mt-4">
    <div class="container">
      <div class="card-columns">
        <div class="card" v-for="item in posts" v-bind:key="item.key" @click="openDetail(item)">  
          <img class="card-img-top" :src="item.urlToImage" alt="Not found image source">
          <div class="card-body">
            <p class="card-text"><small class="text-muted">{{ item.author }} - {{ item.source.name }}</small></p>
            <h5 class="card-title" style="cursor: pointer; color: dodgerblue">{{ item.title }}</h5>
            <p class="card-text"><small class="text-muted">{{ item.publishedAt }}</small></p>
          </div>
        </div>        
      </div>
    </div>
    <button class="btn btn-primary btn-more" @click="loadMore">Load More</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      allPost: [],
      posts: [],
      current: 9
    }
  },
  mounted () {
    axios('https://newsapi.org/v2/top-headlines?country=id&category=technology&apiKey=a050e54685b44bf89ec55dbb472ee1d2', {
      crossDomain: true
    }).then( ({ data }) => {
      this.allPost = data.articles
      data.articles.map((item, key) => {
        if (item.description !== null && this.posts.length < 9) {
          this.posts.push(item)
        }
      })
    })
  },
  methods : {
    loadMore () {
      this.posts = []
      this.current += 9
      this.allPost.map((item, key) => item.description !== null && this.posts.length < this.current ? this.posts.push(item) : '')
    },
    openDetail (data) {
      this.$store.commit('setArticle', data)
      this.$router.replace({ 'path': '/detail' })
    }
  }  
}
</script>


<style lang="scss" scoped>
.btn-more {
  margin: 20px auto;
  display: block;
}
/*
 * Card Columns Masonry - Bootstrap 4
 * https://codepen.io/JacobLett/pen/oZmWdd
 */
/* Medium devices (tablets, 768px and up) The navbar toggle appears at this breakpoint */
@media (min-width: 768px) {  
  .card-columns {column-count: 3;}
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) { 
 .card-columns {column-count: 3;}
}
 
/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {  
   .card-columns {column-count: 3;} 
}

@media (max-width: 768px) {  
  .card {
    width: 110%;
    margin-left: -16px;
    margin-left: -16px;
  }
}



</style>