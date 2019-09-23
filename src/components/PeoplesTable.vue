<template>
  <div class="table" style="width: 100%">
    <hot-table licenseKey="non-commercial-and-evaluation" :data="hotData">
      <hot-column title="Name"></hot-column>
      <hot-column :settings="secondColumnSettings" read-only="true"></hot-column>
      <hot-column title="Email"></hot-column>
      <hot-column title="Address"></hot-column>
      <hot-column title="Phone"></hot-column>
      <hot-column title="Website"></hot-column>
      <hot-column title="Company"></hot-column>
    </hot-table>
    <!-- <div>{{hotData}}</div> -->
    <div class="buttons_block">
      <button @click="recieveData" class="people_btn">загрузить с сервера</button>
      <button class="people_btn">загрузить на сервер</button>
      <button class="people_btn">скачать в .xls</button>
    </div>
  </div>
</template>

<script>
import { HotTable, HotColumn } from '@handsontable/vue';
import Handsontable from 'handsontable';
export default {
  name: "PeoplesTable",
  data:  function() {
    return {
      // hotData: Handsontable.helper.createSpreadsheetData(10, 7),
      hotData: {},
      secondColumnSettings: {
        title: 'Username'
      }
    }
  },
  components: {
    HotTable,
    HotColumn
  },
    methods: {
      recieveData: function() {
        this.axios.get('https://jsonplaceholder.typicode.com/users').then((response) => {
          this.hotData = response.data[0];
          console.log(response.data);
        })
      }
    },
};
</script>

<style lang="less">
@media (min-width: 569px) {
   .ht_clone_top,
  .ht_clone_bottom,
  .ht_clone_left {
    display: none;
  }
  table {
    width: 100%;
    border: 1px solid #E5E5E5 !important;
    height: 400px;
  }
  .wtHider {
    width: 94% !important;
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
}
@media (max-width: 568px) {
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
}
 
</style>