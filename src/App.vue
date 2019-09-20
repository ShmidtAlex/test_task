<template>
  <div id="app">
    <header id="nav">
      <div class="logo_block__wrapper" >
        <div class="croppedLogo"></div>
      </div>
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
    </header>
    <router-view />
    <footer>     
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
  padding: 15px;
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
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  max-width: 1140px;
  height: 100px;
}
.logo_block__wrapper {  
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width:81.91px;
  height: 77px;
}
.croppedLogo {
  background-image: url('assets/logo_full.png');
  background-size: contain;
  background-repeat: no-repeat;
  width: 67.91px;
  height: 63.84px;
  color: transparent;
}
.tabs_group {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 484px;
  height: 32px;
  font-family: Roboto Slab;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 34px;
  text-align: center;
  text-transform: uppercase;
  color: #000000;
}

.user_section {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
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
  max-width: 1140px;
  width: 100%;
  height: 76px;
  left: 0px;
  top: 692px;
  background: #424242;
}

</style>
