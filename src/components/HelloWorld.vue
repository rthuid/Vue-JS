<template>
  <div class="login-page">
    <div class="main-wrap">
      <div class="animation loading" v-if="loading"></div>
      <div class="logo">
        <a routerLink="/"><img src="../assets/opentrends.png" alt="logo"></a>
      </div>    
      <div class="form">
        <form id="app" >
          <h1>Sign in</h1>
          <p v-if="errors.length">
            <b>Please correct the following error(s):</b>
            <ul>
              <li v-for="error in errors">{{ error }}</li>
            </ul>
          </p>
          <div class="form-group" id="email-container">
            <input type="text" class="form-control" placeholder="Username" v-model="formName" @keyup.enter="login()">
          </div>
          <div class="form-group" id="password-container">
            <input type="password" class="form-control" placeholder="Password" v-model="formPassword" @keyup.enter="login()">
          </div>
          <div class="btn btn-block btn-primary" @click="login()">Login</div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'login',
  props: {
    msg: String
  },
  data:  ()=> {
    return {
      formName: '',
      formPassword: '',
      loading: false,
      username: 'user',
      password: '12345',
      errors: [],
      logObj: {
        'name': false,
        'password': false
      }
    }
  },
  methods: {
    login() {
      this.loading = true;
      this.errors = [];
      setTimeout(() => {
        if (this.username == this.formName) {
          this.logObj.name = true
        } else {
          this.logObj.name = false
          this.loading = false;
          this.errors.push('valid username required');
        }
        if (this.password == this.formPassword) {
          this.logObj.password = true
        } else {
          this.logObj.password = false
          this.loading = false;
          this.errors.push('valid password required');
        }
        if (this.logObj.password && this.logObj.name) {
          this.loading = false;
          // alert('in')
          this.$router.push('home')
        }
      }, 2000);
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped  lang="scss">
@import '../sass/_variables.scss';
@import '../sass/_mixins.scss';
.login-page{
    min-height: 100vh;
    @include flex-master($flex-direction:row,$flex-wrap:nowrap,$align-content:center,$align-items:center);
    @include gradient();
    -webkit-justify-content: center;
    -ms-flex-pack: center;
    justify-content: center;
    -webkit-align-content: center;
    -ms-flex-line-pack: center;
    align-content: center;
    -webkit-align-items: center;
    -ms-flex-align: center;
    align-items: center;
    padding: $padding*2;
    .main-wrap{
        width: 350px;
        max-width: 100%;
        padding: $padding*2;
        background: $color-white;
        border-radius: $border-radius;
        border: 1px solid $color-border;
        overflow: hidden;
        position: relative;
        @include box-shadow();
        .animation{
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: lighten($color-2, 40);
            &.loading{
                display: block;
                &:before{
                    content: '';
                    display: block;
                    height: 4px;
                    width: 100px;
                    background: lighten($color-1, 5);
                    @extend .loaging-animation;
                }
            }
        }
        h1{
            font-size: $font-size-large;
            color: $color-1;
            font-weight: bold;
        }
        .logo{
            padding-bottom: $padding*2;
        }
        .create-account{
            padding-top: $padding;
            @include flex-master($flex-direction:row,$flex-wrap:nowrap,$align-content:stretch,$align-items:center);
        }
    }
}
</style>
