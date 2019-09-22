<template>
  <div id="app">
    <header id="nav">
      <div class="header_container">
        <button class="menu_collapsed" :class="{_expanded: isMenuExpanded}" @click="isMenuExpanded = !isMenuExpanded">
          <div class="small">
            <span class="sm"></span>
            <span class="sm"></span>
            <span class="sm"></span>
          </div>
          <div class="big">
            <span class="bg"></span>
            <span class="bg"></span>
            <span class="bg"></span>
          </div>
        </button>
        <div class="logo_block__wrapper" >
          <div class="croppedLogo"></div>
        </div>
        <!-- <div class="right_block_container"> -->
          <div class="tabs_group" :class="{ tabs_group_active: isMenuExpanded }">
            <router-link to="/">media</router-link> 
            <router-link to="/about">digital</router-link>
            <router-link to="/social">social</router-link>
            <router-link to="/commerce">commerce</router-link>
            <router-link to="/people">people</router-link> 
          </div>
          <div class="user_section">
          <!--   вообще конечно, это не здесь должно изменяться, а при загрузке компонента с внутренней страницей пользователя
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
            <div class="circle">
              <div class="small-circle"></div>
            </div>
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
        isMenuExpanded: false,
      }
    },
  };
</script>
<style lang="less">
@media (min-width: 569px) {
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
    .menu_collapsed {
      display: none;
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
    .copyrights:hover {
      color: #DFC800;
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
            // &:extend(.vk);
           background-image: url("assets/vk-hover.png");
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
              background-position-y: 10px;
              background-position-x: 17px;
              width: 30px;
              height: 30px;
            }
            .small-circle:hover {
              background-image:url("assets/insta-hover-small.png");
            }
          }
          .circle:hover {
            background-image: url("assets/instagramm-hover.png");
          }
        }
        .instagramm:hover {
          background-image: url("assets/fra-hover.png");
        }
        .facebook {
          background-image: url("assets/facebook.png");
          background-repeat:no-repeat;
          background-position-y: 8px;
          background-position-x: 11px;
          width: 30px;
          height: 30px;
        }
        .facebook:hover {
          background-image: url("assets/face-hover.png");
        }
      }
      .icon_wrapper:hover {
        background-image: url("assets/circle-hover.png");
      }
    }
  }
}
@media (max-width: 568px) {
   #app {
    // font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    display: flex;
    flex-direction: column;
    align-items:center;
  }
  #nav {
    width: 100%;
    height: 60px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background: #FFFFFF;
    border: 1px solid #FFFFFF;
    position: fixed;
    top: 0;
    left: 0;
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
      height: 100%;
      width: 100%;
      margin: 0 20px;
    }

  }
  .menu_collapsed {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 28px;
    height: 22px;
    order: 1;
    border: none;
    padding: 0;
    background-color: transparent;
    outline: none;
    .small {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: stretch;
      opacity: 1;
      transition: opacity .5s ease-in-out;
      .sm {
        width: 8px;
        height: 6px;
        background: #C4C4C4;
        border: 1px solid #ffffff;
      }
    }
    .big {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: stretch;
      opacity: 1;
      transition: opacity .5s ease-in-out;
      .bg {
        width: 18px;
        height: 6px;
        background: #C4C4C4;
        border: 1px solid #ffffff;
      }
    }
  }
  ._expanded {
    background-image: url('assets/close.svg');
    background-size: contain;
    background-repeat: no-repeat;
    .small {
      opacity: 0;
    }
    .big {
      opacity: 0;
    }
  }
  .logo_block__wrapper {  
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width:68px;
    height: 50px;
    margin-bottom: 1px;
    order: 2;
    .croppedLogo {
      background-image: url('assets/croppedLogo.png');
      background-size: contain;
      background-repeat: no-repeat;
      width: 100%;
      height: 100%;
      color: transparent;
    }
  }
  .tabs_group {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    width: 100%;
    height: 0px;
    top: 60px;
    left: 0;
    font-family: Roboto Slab;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    background: #FFFFFF;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.1);
    border-radius: 0px 0px 4px 4px;
    text-align: center;
    text-transform: uppercase;
    color: #000000;
    transition: all 1s ease-in-out;
    opacity: 0;
    overflow: hidden;
    // a:first-child {
    //   margin-left: 40px;
    // }
    // a:last-child {
    //   margin-right: 40px;
    // }
    // padding: 0 20px;
  }
  .tabs_group_active {
    height: 250px;
    opacity: 1;
    border-top: 1px solid #E5E5E5;
    padding: 24px 0 24px;
  }
  .user_section {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    order:3;
    .user_logo {
      background-image: url("assets/user_default.png");
      width: 30px;
      height: 30px;
    }
    .user_logo:hover {
      background-image: url("assets/user_hover.png");
    }
    .user_logo._active {
      background-image: url("assets/user_active.png");
    }
  }
  footer {
    width: 100%;
    height: 76px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    background: #424242;
    position: fixed;
    bottom: 0;
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
      margin-left: 19px;
    }
    .copyrights:hover {
      color: #DFC800;
    }
    .social_icons {
      width: 136px;
      height: 30px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      margin-right: 19px;
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
            // &:extend(.vk);
           background-image: url("assets/vk-hover.png");
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
              background-position-y: 10px;
              background-position-x: 17px;
              width: 30px;
              height: 30px;
            }
            .small-circle:hover {
              background-image:url("assets/insta-hover-small.png");
            }
          }
          .circle:hover {
            background-image: url("assets/instagramm-hover.png");
          }
        }
        .instagramm:hover {
          background-image: url("assets/fra-hover.png");
        }
        .facebook {
          background-image: url("assets/facebook.png");
          background-repeat:no-repeat;
          background-position-y: 8px;
          background-position-x: 11px;
          width: 30px;
          height: 30px;
        }
        .facebook:hover {
          background-image: url("assets/face-hover.png");
        }
      }
      .icon_wrapper:hover {
        background-image: url("assets/circle-hover.png");
      }
    }
  }
}

</style>
