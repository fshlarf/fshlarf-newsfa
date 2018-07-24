<template>
  <div class="mt-3">
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="card detail">
            <img :src="article.urlToImage" alt="Card image cap" class="card-img-top img-fluid">
            <div class="card-body">
                <p class="card-text"><small class="text-muted">{{ article.publishedAt }} - {{ article.author }} - {{ article.source.name }}</small></p>
                <h5 class="card-title">{{ article.title }}</h5>
                <p class="card-text">{{ article.description }}</p>
                <p>
                    sumber:
                    <a :href="article.url">{{article.url}}</a>
                </p>
            </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    layout: 'navbarback',
    async asyncData({ params, error }) {
    try {
      const { data } = await axios.get(`http://localhost:4000/userdata/${params.id}`)
      return {user: data}
    } catch (e) {
      error({ message: 'User not found', statusCode: 404 })
    }
  }
}
</script>