
<template>
  <div class="home">
    <div class="background_container">
      <div class="background">
        <HelloWorld  />
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
@media (min-width: 569px) {
  .home {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-top: 3px;
    background-color: #ffffff;
    height: 100%;
  }
  .background_container {
    width: 100%;
    height: 100%;
    background: #FFFFFF;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: flex-start;
    margin-bottom: 12px;
  }

  .background {
    background-image: url("../assets/Background.png");
    background-size: cover;
    background-position: bottom;
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
}
@media (max-width: 568px) {
  .home {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    height: 100%;
    overflow: hidden;
  }
  .background_container {
    width: 100%;
    height: 100%;
    background: #FFFFFF;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: flex-start;
    margin-bottom: 5px;
  }

  .background {
    background: #F6F6F6;
    background-size: cover;
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
}  
</style>