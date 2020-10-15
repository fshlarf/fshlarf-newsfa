
<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
            <li class="nav-item active">
                <a class="nav-link" href="">Home <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="" @click.prevent="$router.push('/entertainment')">Entertainment</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="" @click.prevent="$router.push('/about')">About</a>
            </li>
            </ul>
            <form class="form-inline my-2 my-lg-0">
            <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
            <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
            </form>
        </div>
    </nav>
</template>

<script>
export default {
    state : {
        state : 'close'
    },
    methods : {
        goBack () {
            this.$store.commit('setArticle', {})
            this.$router.replace({ 'path' : '/' })
        },
    },
}
</script>

<style lang="scss" scoped>
.navbar-brand {
  span {
    font-size: 32px;
    
  }
}

.img-nav {
    width: 20px;
    margin-left: 10px;
    margin-right: -50px;
}

.navbar {
    background-color: lightseagreen;
}

.nav-link {
    color: white;
    margin-left:0;
}

.nav-link.tech{
    color: white;
    text-align: left;
    margin-left: -400px;
    
}

.nav-link.entertain{
    color: white;
    text-align: left;
    margin-left: -440px;
    
}

.nav-link.about{
    color: white;
    text-align: left;
    margin-left: -440px;
    
}



@media (max-width: 768px) {  
    .nav-link.tech{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }

    .nav-link.entertain{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }

    .nav-link.about{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }
}
/* Large devices (desktops, 992px and up) */
@media (max-width: 992px) { 
    .nav-link.tech{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }

    .nav-link.entertain{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }

    .nav-link.about{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }
}
 
/* Extra large devices (large desktops, 1200px and up) */
@media (max-width: 1200px) {  
    .nav-link.tech{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }

    .nav-link.entertain{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }

    .nav-link.about{
        color: white;
        text-align: left;
        margin-left: 0;
        
    }
}

.navbar-toggler-icon {
    color:  white;
}




</style>