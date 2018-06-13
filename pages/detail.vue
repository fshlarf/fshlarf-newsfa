
<template>
  <div class="mt-4">
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="card">
            <img :src="article.urlToImage" alt="Card image cap" class="card-img-top img-fluid">
            <div class="card-body">
                <p class="card-text"><small class="text-muted">{{ article.publishedAt }} - {{ article.author }} - {{ article.source.name }}</small></p>
                <h5 class="card-title">{{ article.title }}</h5>
                <p class="card-text">{{ article.description }}</p>
                <p>
                    sumber:
                    <a href="">{{ article.url }}</a>
                </p>
            </div>
        
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    computed: {
        article () { 
            return this.$store.state.article 
        },
        
    }
 
}
</script>

<style>

.card {
    width: 600px;
}

.img-fluid {
    object-fit: cover;
}

@media (min-width: 768px) {  
    .col-8 {
      width: 100px;
    }
}

</style>