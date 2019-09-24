<template>
  <div class="people">
    <h3>Посетители</h3>
    <div class="table_block">
      <PeoplesTable />
    </div>
    <div class="buttons_block">
      <button @click="recieveData" class="people_btn">загрузить с сервера</button>
      <button class="people_btn">загрузить на сервер</button>
      <button class="people_btn">скачать в .xls</button>
    </div>
  </div>
</template>
<script>
  // import Handsontable from 'handsontable';
  import PeoplesTable from "@/components/PeoplesTable.vue";
  export default {
    name: "People",
    components: {
      PeoplesTable
    },
    data: function() {
      return {

      }
    },
    methods: {
      recieveData: function() {
        this.axios.get('https://jsonplaceholder.typicode.com/users').then((response) => {
          console.log(response.data)
        })
      }
    }
  };
</script>
<style scoped lang="less">
@media (min-width: 569px) {
  
  .people {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    background-color: #ffffff;
    width: 100%;
    height: calc(100% - 60px);
    margin: 3px 0 0;
    overflow: hidden;
    h3 {
      margin-left: 32px;
      text-transform: uppercase;
      font-family: Roboto Slab;
      font-style: normal;
      font-weight: bold;
      font-size: 18px;
      color: #000000;
    }
    .table_block {
      margin-left: 32px;
      width: 100%;
      table {
        width: 100%;
        height: 100%;
      }
    }    
    
  }
}
@media (max-width: 568px) {
  .people {
    height: 100%;
    padding: 66px 0;
    width: 83%;
    overflow-x: scroll;
    overflow-y: hidden;
    .table_block {
      height: fit-content;
      margin: 0;
    }
    .buttons_block {
      margin: -145px 0 0;
    }
  }
}
.buttons_block {
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      align-items: center;
      margin-left: 32px;
      width: 100%;
      height: 150px;
      flex-wrap: wrap;
      .people_btn {
        width: 255px;
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
        margin: 0 20px 0px 0;
      }
      .people_btn:hover {
        background-color: #424242;
      }
      .people_btn:active {
        background-color: #000000;
      }
    }
</style>