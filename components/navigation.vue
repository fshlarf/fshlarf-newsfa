<template>
    <nav class="navbar navbar-padding navbar-expand-lg navbar-light">
        <div v-if="!$store.state.article.title" class="container">
            <a class="navbar-brand" style="color: white" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation" @click="openHome">Newsfa</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <i class="fa fa-navicon" style="color: white"></i>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <!-- Tech -->
                    <a class="nav-link" style="color: white" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation" @click="openHome">Technology </a>
                </li>
                <li class="nav-item">
                    <!-- Enter -->
                    <a class="nav-link" style="color: white" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation" @click="openEntertain">Entertainment</a>
                </li>
                <li class="nav-item">
                    <!-- About -->
                    <a class="nav-link" style="color: white" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation" @click="openAbout">About</a>
                </li>
                </ul>
                <form class="form-inline my-2 my-lg-0">
                    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
                    <button class="btn btn-outline-dark my-2 my-sm-0" type="submit" style="color: white">Search</button>
                </form>
            </div>
        </div>
        <div v-else class="container">
            <a class="navbar-brand" href="" @click="goBack()">
                <span class="ion-android-arrow-back" style="color:white; font-size: 20px;"> Back</span>
            </a>
        </div>
    </nav>
</template>

<script>
export default {
    state : {
        state : 'close'
    },
    methods : {
        openHome () {
            this.$router.replace({'path':'/'})
        },
        goBack () {
            this.$store.commit('setArticle', {})
            this.$router.replace({ 'path' : '/' })
        },
        openAbout(){
            this.$router.replace({ 'path' : '/about' })
        },
        openEntertain(){
            this.$router.replace({ 'path' : '/entertainment' })
        }
    }
}
</script>

<style lang="scss" scoped>
.navbar {
    background-color: black;
}
.nav-link {
    color: white;
    margin-left:0;
}
.navbar-toggler-icon {
    color:  white;
}
.nav-item {
    cursor: pointer;
}
.nav-item:active {
    background-color: rgba(0, 0, 0, 0.336);
}
.nav-item:visited {
    background-color: rgba(0, 0, 0, 0.336);
}

@import url("https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css");
body{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: #F0AD4E;
}
label{
  position: relative;
  display: inline-block;
  background-color: #fff;
  padding: 5px 12px;
  transition: all 1s ease;
  border-radius: 25px;
  box-shadow: 1px 1px 5px rgba(0,0,0,0.5);
  &::after{
    content: '';
    display: block;
    height: 2px;
    width: 80%;
    background-color: #F0AD4E;
    transition: all 1s ease 0.5s;
  }
  input{
    transition: width 1s ease, opacity 0.5s ease 0.5s;
    opacity: 1;
    width: 180px;
    height: 25px;
    border: 0;
    outline: none;
    color: darken(#F0AD4E, 25)
  }
  i{
    position: absolute;
    top: 11px;
    right: 11px;
    color: #333;
    cursor: pointer;
  }
  &[data-state="close"]{
    border-radius: 30px;
    padding: 5px 5px;
     transition: all 1s ease;
    &::after{
      width: 0%;
      transition: all 0.3s ease;
    }
    i{
      pointer-events: none;
    }
    input{
      width: 28px;
      height: 25px;
      opacity:0;
      cursor: pointer;
      transition: opacity 0.5s ease, width 1s ease;
      -webkit-appearance:none
    } 
  }
}
</style>