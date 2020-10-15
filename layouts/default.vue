
<template>
  <div>
    <!-- Navigation -->
    <Navigation/>
    <!-- Content -->
    <div class="container content">
      <!-- Content -->
      <nuxt/>
      
    </div>
    <!-- Footer -->
    <div class="footer">
      <p>
        Copyright
      </p>
      <img class="img-mail" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ab/Gmail_Icon.svg/2000px-Gmail_Icon.svg.png" alt="img gmail">
      <span>
        faishal1303@gmail.com
      </span>
    </div>
  </div>
</template>

<script>
import Navigation from '~/components/navigation.vue'
export default {
  components: {
    Navigation,
  }
}
</script>

<style>
.img-mail {
  width : 20px;
}
</style>
