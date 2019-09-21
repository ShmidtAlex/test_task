<template>
  <div id="app">
    <header id="nav">
      <div class="header_container">
        <div class="logo_block__wrapper" >
          <div class="croppedLogo"></div>
        </div>
        <!-- <div class="right_block_container"> -->
          <div class="tabs_group">
            <router-link to="/">media</router-link> 
            <router-link to="/about">digital</router-link>
            <router-link to="/social">social</router-link>
            <router-link to="/commerce">commerce</router-link>
            <router-link to="/people">people</router-link> 
          </div>
          <div class="user_section">
            <!-- вообще конечно, это не здесь должно изменяться, а при загрузке компонента с внутренней страницей пользователя
            но пока так -->
            <div @click="isUserLoggedIn = !isUserLoggedIn" class="user_logo" :class="{_active: isUserLoggedIn}"></div>
          </div>
        <!-- </div> -->
      </div>
    </header>
    <router-view />
    <footer>
      <div class="copyrights">(c) Publicis Groupe 2019</div> 
      <div class="social_icons">
        <div class="icon_wrapper">
          <div class="vk"></div>
        </div>
        <div class="icon_wrapper">
          <div class="instagramm">
            <div class="circle"></div>
            <div class="small-circle"></div>
          </div>
        </div>
        <div class="icon_wrapper">
          <div class="facebook"></div>
        </div>
      </div>    
    </footer>
  </div>
</template>
<script>
  export default {

    data: function() {
      return {
        isUserLoggedIn: false,
      }
    },
  };
</script>
<style lang="less">
@media (max-width: 1140px) {
  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    display: flex;
    flex-direction: column;
    align-items:center;
  }
  #nav {
    // padding: 15px;
    width: 100%;
    height: 100px;
    width: 100%;
    height: 100px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    a {
      font-weight: bold;
      color: #2c3e50;
      text-decoration: none;
      &.router-link-exact-active {
        color: #85754A;
      }
    }
    a:hover {
      text-decoration: underline;
      font-weight: bold;
    }
    .header_container {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      height: 77%;
      margin: 0 32px;
      // border: 1px solid;
      width: 100%;
    }
  }
  .logo_block__wrapper {  
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width:81.91px;
    height: 77px;
    margin-bottom: 1px;
    .croppedLogo {
      background-image: url('assets/logo_full.png');
      background-size: contain;
      background-repeat: no-repeat;
      width: 100%;
      height: 100%;
      color: transparent;
    }
  }
  
  .tabs_group {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-self: flex-end;
    width: 484px;
    height: 32px;
    font-family: Roboto Slab;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    // line-height: 34px;
    text-align: center;
    text-transform: uppercase;
    color: #000000;
    // border: 1px solid black;
    margin-bottom: -7px;
    a:first-child {
      margin-left: 40px;
    }
    a:last-child {
      margin-right: 40px;
    }
    // padding: 0 20px;
  }

  .user_section {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: center;
    width: 81.91px;
    height: 77px;
    margin-bottom: -7px;
    justify-self: flex-end;
    // border: 1px solid black;
    .user_logo {
      background-image: url("assets/user_default.png");
      width: 30px;
      height: 30px;
      margin-top: 13px;
    }
    .user_logo:hover {
      background-image: url("assets/user_hover.png");
    }
    .user_logo._active {
      background-image: url("assets/user_active.png");
    }
  }
  footer {
    max-width: 1140px;
    width: 100%;
    height: 76px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    background: #424242;
    .copyrights {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items:center;
      width: 130px;
      height: 25px;
      font-family: Roboto Slab;
      font-style: normal;
      font-weight: normal;
      font-size: 10px;
      line-height: 24px;
      text-align: center;
      text-transform: uppercase;
      color: #C4C4C4;
      margin-left: 32px;
    }
    .social_icons {
      width: 136px;
      height: 30px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      margin-right: 32px;
      .icon_wrapper {
        width: 30px;
        height: 30px;
        background-image: url("assets/circle.png");
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        .vk {
          background-image: url("assets/vk.png");
          background-repeat:no-repeat;
          background-position-y: 10px;
          background-position-x: 6px;
          width: 30px;
          height: 30px;
        }
        .vk:hover {

        }
        .instagramm {
          background-image: url("assets/fra.png");
          background-repeat:no-repeat;
          background-position-y: 9px;
          background-position-x: 9px;
          width: 30px;
          height: 30px;
          .circle {
            background-image: url("assets/instagramm.png");
            background-repeat:no-repeat;
            background-position-y: 11px;
            background-position-x: 11px;
            width: 30px;
            height: 30px;
            .small-circle {
              background-image: url("assets/insta-small.png");
              background-repeat:no-repeat;
              background-position-y: 11px;
              background-position-x: 11px;
              width: 30px;
              height: 30px;
            }
            .small-circle:hover {
              background-image:url("assets/insta-hover-small.png");
            }
          }
          .circle:hover {
            background-image: url("assets/fra-hover.png");
            // background-position-y: 0px;
            // background-position-x: 0px;
          }
        }
        .instagramm:hover {
          // background-image: url("assets/circle-hover.png");
          // background-position-y: 0px;
          // background-position-x: 0px;
        }
        .facebook {
          background-image: url("assets/facebook.png");
          background-repeat:no-repeat;
          background-position-y: 8px;
          background-position-x: 11px;
          // background-size: contain;
          width: 30px;
          height: 30px;
        }
      }
      .icon_wrapper:hover {
        background-image: url("assets/circle-hover.png");
      }
    }
  }
}


</style>
