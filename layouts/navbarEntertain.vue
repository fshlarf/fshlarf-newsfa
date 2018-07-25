<template>
  <div>
    <!-- Navigation -->
    <NavigationEntertainment/>
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
import NavigationEntertainment from '~/components/NavigationEntertainment.vue'
import Banner from '~/components/banner.vue'
export default {
  components: {
    NavigationEntertainment,
    Banner
  }
}
</script>

<style>
.img-mail {
  width : 20px;
}
</style>
