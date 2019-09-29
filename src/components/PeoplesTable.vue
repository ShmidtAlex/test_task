<template>
  <div class="wrapper">
    <div class="table" style="width: 100%">
      <hot-table licenseKey="non-commercial-and-evaluation" ref="hotTableComponent" :settings="hotSettings">
      </hot-table>
    </div>
    <!-- <div>{{dataObject}}</div> -->
    <div class="buttons_block">
      <button @click="recieveData" class="people_btn">загрузить с сервера</button>
      <button class="people_btn">загрузить на сервер</button>
      <button class="people_btn">скачать в .xls</button>
    </div>
  </div>
  
</template>

<script>
import { HotTable, HotColumn } from "@handsontable/vue";
import Handsontable from 'handsontable';
//ЭТО ДЛЯ ТЕСТИРОВАНИЯ, СТАТИЧЕСКИЙ ОБЪЕКТ
// let dataObject = [
  // {
  //   id: 1,
  //   name: "Leanne Graham",
  //   username: "Bret",
  //   email: "Sincere@april.biz",
  //   address: {
  //     street: "Kulas Light",
  //     suite: "Apt. 556",
  //     city: "Gwenborough",
  //     zipcode: "92998-3874",
  //     geo: {
  //       lat: "-37.3159",
  //       lng: "81.1496"
  //     }
  //   },
  //   phone: "1-770-736-8031 x56442",
  //   website: "hildegard.org",
  //   company: {
  //     name: "Romaguera-Crona",
  //     catchPhrase: "Multi-layered client-server neural-net",
  //     bs: "harness real-time e-markets"
  //   }
  // },
  // {
  //   id: 2,
  //   name: "Ervin Howell",
  //   username: "Antonette",
  //   email: "Shanna@melissa.tv",
  //   address: {
  //     street: "Victor Plains",
  //     suite: "Suite 879",
  //     city: "Wisokyburgh",
  //     zipcode: "90566-7771",
  //     geo: {
  //       lat: "-43.9509",
  //       lng: "-34.4618"
  //     }
  //   },
  //   phone: "010-692-6593 x09125",
  //   website: "anastasia.net",
  //   // company: {
  //     name: "Deckow-Crist",
  //     catchPhrase: "Proactive didactic contingency",
  //     bs: "synergize scalable supply-chains"
  //   }
  // },
//   
// ]
export default {
  name: "PeoplesTable",
  // props: [ 'dataObject' ],
  // extends: BaseEditorComponent,
  components: {
    HotTable,
    HotColumn,
  },
  data: function() {
    return {
      dataObject: {},
      hotSettings: {
        rowHeaders: true,
        columns: [
          {
            data: 'name',
            type: 'text'
          },
          {
            data: 'username',
            type: 'text'
          },
          {
            data: 'email',
            type: 'text'
          },
          {
            data: 'phone',
            type: 'text'
          },
          {
            data: 'website',
            type: 'text'
          },
        ],
        stretchH: 'all',
        width: "100%",
        autoWrapRow: true,
        height: 487,
        maxRows: 22,
        rowHeaders: true,
        colHeaders: [
          'Name',
          'Username',
          'Email',
          'Phone',
          'Website'
        ]
      },
    }
  },
  methods: {
    recieveData: function() {
      this.axios.get('https://jsonplaceholder.typicode.com/users').then((response) => {
        // console.log( response.data);
        var data = response.data;
         // console.log( data);
        this.$refs.hotTableComponent.hotInstance.loadData(data);
      })
    }
  }
};
</script>

<style lang="less">
  .ht_clone_top,
  .ht_clone_bottom,
  .ht_clone_left {
    display: none;
  }
  .wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    height: 100%;
  }
  
  table {
    width: 100%;
    border: 1px solid #E5E5E5 !important;
    height: 400px;
  }
  .wtHolder {
      height: fit-content !important;
      }
  .wtHider {
    width: 94% !important;
  }
  @media (min-width: 569px) {
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
  
  // .wtSpreader {
  //   width: 100% !important;
  // }
</style>