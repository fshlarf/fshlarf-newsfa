
<template>
    <nav class="navbar navbar-expand-lg">
        <div v-if="!$store.state.article.title" class="container">
            <img class="img-nav" src="https://www.freeiconspng.com/uploads/rocket-png-22.png" alt="">
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mr-auto">
                <li class="nav-item active">
                    <a class="nav-link" href="#" @click="goBack()">Technology <span class="sr-only">(current)</span></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#" @click="openEntertain()">Entertainment</a>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                    Dropdown
                    </a>
                    <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                    <a class="dropdown-item" href="#">Action</a>
                    <a class="dropdown-item" href="#">Another action</a>
                    <div class="dropdown-divider"></div>
                    <a class="dropdown-item" href="#">Something else here</a>
                    </div>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#" @click="openAbout()">About</a>
                </li>
                </ul>
                <form class="form-inline my-2 my-lg-0">
                <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-primary my-2 my-sm-0" type="submit">Search</button>
                </form>
            </div>
        </div>
        
        
        
        <!-- <div v-if="!$store.state.article.title" class="container">
            <img class="img-nav" src="https://www.freeiconspng.com/uploads/rocket-png-22.png" alt="">
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#myNavbar" aria-controls="myNavbar" aria-expanded="false" aria-label="Toggle navigation">
                 <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="myNavbar">
            <ul class="dropdown-menu nav navbar-nav">
                <li class="active">
                    <a class="nav-link" href="#" @click="goBack()">Technology <span class="sr-only">(current)</span></a>
                </li>
                <li class="nav-item">
                     <a class="nav-link" href="#" @click="openEntertain()">Entertainment</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#" @click="openAbout()">About</a>
                </li>
            </ul>
            </div>
        </div> -->
      
        <div v-else class="container">
            <a class="navbar-brand" href="#" @click="goBack()">
            <span class="ion-android-arrow-back" style="color:white"></span>
            </a>
        </div>
    </nav>
</template>

<script>
export default {
    methods : {
        goBack () {
            this.$store.commit('setArticle', {})
            this.$router.replace({ 'path' : '/' })
        },
        openAbout(){
            this.$router.replace({ 'path' : '/about' })
        },
        openEntertain(){
            this.$router.replace({ 'path' : '/entertainment' })
        },
    }
}
</script>

<style lang="scss" scoped>
.navbar-brand {
  span {
    font-size: 32px;
    
  }
}
.img-nav {
    width: 30px;
}
.navbar {
    background-color: grey
    ;
}

.nav-link {
    color: white
}

.navbar-toggler-icon {
    color:  white;
}


</style>