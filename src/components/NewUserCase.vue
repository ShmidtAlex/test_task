<template>
   <div class="exist_user_wrapper">
    <div class="user_data_wrapper">
        <input type="text" class="user_data" name="login" required="true" placeholder="логин">
        <input type="password" class="user_data" name="password" required="true" placeholder="пароль">      
    </div>
    <div class="button_wrapper">
      <button type="submit" class="submit_button"><span class="normal_font">войти</span></button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ExistUserCase",
  props: {
    msg: String
  },
  data: function() {
    return {

    }
  },
  methods: {
   
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.exist_user_wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 100%;
  width: 100%;
}
.user_data_wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  height: 54%;
  border-radius: 4px; 
  margin-top: -4px; 
  .user_data {
    width: 346px;
    height: 44px;
    left: 339px;
    top: 349px;
    background: #FFFFFF;
    border: 1px solid #E5E5E5;
    box-sizing: border-box;
    border-radius: 4px;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    font-family: Roboto;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 26px;
    padding: 20px;
    color: #C4C4C4;
  }
  .user_data:first-child {
    margin-top: 10px;
  }
}
.button_wrapper {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: horizontal;
    -webkit-box-direction: normal;
    -ms-flex-direction: row;
    flex-direction: row;
    align-items: flex-start;
    height: 31%;
    .submit_button {
      width: 184px;
      height: 46px;
      background: #86764B;
      border-radius: 4px;
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      outline: none;
      border: none;
      font-family: Roboto;
      font-style: normal;
      font-weight: bold;
      text-transform: uppercase;
      color: #ffffff;
      .normal_font {
        width: 47px;
        height: 31px;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        font-size: 14px;
        transform: scale(1, 0.9);
      }
    }
  }
</style>