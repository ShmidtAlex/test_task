
<template>
  <div class="home">
    <div class="background_container">
      <div class="background">
        <HelloWorld msg="Welcome to Your Vue.js App" />
      </div>
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  components: {
    HelloWorld
  }
};
</script>
<style>
  .home {
    width: 100%;
    /*max-width: 1140px;*/
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .background_container {
    width: 1140px;
    height: 100%;
    background: #FFFFFF;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: flex-start;
    margin-bottom: 5px;
  }

  .background {
    background-image: url("../assets/Background.png");
    background-size: cover;
    width: 100%;
    height: 580px;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
</style>