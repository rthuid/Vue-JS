<template>
  <div class="home">
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
        <router-link class="nav-link" to="/home">
            <img src="../assets/opentrends01.png" alt="logo">
        </router-link>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <!-- <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a> -->
                    <router-link class="nav-link" to="/home">Home</router-link>
                </li>
                <li class="nav-item">
                    <!-- <a class="nav-link" href="#">Link</a> -->
                    <router-link class="nav-link" to="/about">About</router-link>
                </li>
                </li>
                <li class="nav-item last">
                    <!-- <a class="nav-link" href="#">Link</a> -->
                    <router-link class="nav-link" to="/">Logout</router-link>
                </li>
            </ul>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'mainHeader'
}
</script>
<style lang="scss">
.navbar-nav.mr-auto{
    width: 100%;
    .nav-item.last {
        -webkit-flex: 1 1 auto;
        -ms-flex: 1 1 auto;
        flex: 1 1 auto;
        text-align: right;
        a{
            display: inline-block;
        }
    }
}
    .nav-item{
        a {
            color: #fff;
            margin: 0 15px;
        }
    } 
</style>

