<template>
  <div class="wrapper">
    <div class="table" style="width: 100%">
      <hot-table licenseKey="non-commercial-and-evaluation" :settings="hotSettings">
        <hot-column >
          <custom-editor :width="250" hot-editor></custom-editor>  
        </hot-column>
        <hot-column >
          <custom-editor hot-editor></custom-editor> 
        </hot-column>
        <hot-column :width="250">
          <custom-editor hot-editor></custom-editor>  
        </hot-column>
        <hot-column :width="250">
          <custom-editor hot-editor></custom-editor>  
        </hot-column>
        <hot-column :width="250">
          <custom-editor :width="250" hot-editor></custom-editor>  
        </hot-column>
        <hot-column :width="250">
          <custom-editor hot-editor></custom-editor>  
        </hot-column>
        <hot-column :width="250">
          <custom-editor hot-editor></custom-editor>  
        </hot-column>
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
import { HotTable, HotColumn, BaseEditorComponent } from '@handsontable/vue';
import Handsontable from 'handsontable';
let dataObject = [
  {
    id: 1,
    name: "Leanne Graham",
    username: "Bret",
    email: "Sincere@april.biz",
    address: {
      street: "Kulas Light",
      suite: "Apt. 556",
      city: "Gwenborough",
      zipcode: "92998-3874",
      geo: {
        lat: "-37.3159",
        lng: "81.1496"
      }
    },
    "phone": "1-770-736-8031 x56442",
    "website": "hildegard.org",
    company: {
      name: "Romaguera-Crona",
      catchPhrase: "Multi-layered client-server neural-net",
      bs: "harness real-time e-markets"
    }
  },
  {
    id: 2,
    name: "Ervin Howell",
    username: "Antonette",
    email: "Shanna@melissa.tv",
    address: {
      street: "Victor Plains",
      suite: "Suite 879",
      city: "Wisokyburgh",
      zipcode: "90566-7771",
      geo: {
        lat: "-43.9509",
        lng: "-34.4618"
      }
    },
    "phone": "010-692-6593 x09125",
    "website": "anastasia.net",
    company: {
      name: "Deckow-Crist",
      catchPhrase: "Proactive didactic contingency",
      bs: "synergize scalable supply-chains"
    }
  },
  {
    id: 3,
    name: "Clementine Bauch",
    username: "Samantha",
    email: "Nathan@yesenia.net",
    address: {
      street: "Douglas Extension",
      suite: "Suite 847",
      city: "McKenziehaven",
      zipcode: "59590-4157",
      geo: {
        lat: "-68.6102",
        lng: "-47.0653"
      }
    },
    "phone": "1-463-123-4447",
    "website": "ramiro.info",
    company: {
      name: "Romaguera-Jacobson",
      catchPhrase: "Face to face bifurcated interface",
      bs: "e-enable strategic applications"
    }
  },
  {
    id: 4,
    name: "Patricia Lebsack",
    username: "Karianne",
    email: "Julianne.OConner@kory.org",
    address: {
      street: "Hoeger Mall",
      suite: "Apt. 692",
      city: "South Elvis",
      zipcode: "53919-4257",
      geo: {
        lat: "29.4572",
        lng: "-164.2990"
      }
    },
    "phone": "493-170-9623 x156",
    "website": "kale.biz",
    company: {
      name: "Robel-Corkery",
      catchPhrase: "Multi-tiered zero tolerance productivity",
      bs: "transition cutting-edge web services"
    }
  },
  {
    id: 5,
    name: "Chelsey Dietrich",
    username: "Kamren",
    email: "Lucio_Hettinger@annie.ca",
    address: {
      street: "Skiles Walks",
      suite: "Suite 351",
      city: "Roscoeview",
      zipcode: "33263",
      geo: {
        lat: "-31.8129",
        lng: "62.5342"
      }
    },
    "phone": "(254)954-1289",
    "website": "demarco.info",
    company: {
      name: "Keebler LLC",
      catchPhrase: "User-centric fault-tolerant solution",
      bs: "revolutionize end-to-end systems"
    }
  },
  {
    id: 6,
    name: "Mrs. Dennis Schulist",
    username: "Leopoldo_Corkery",
    email: "Karley_Dach@jasper.info",
    address: {
      street: "Norberto Crossing",
      suite: "Apt. 950",
      city: "South Christy",
      zipcode: "23505-1337",
      geo: {
        lat: "-71.4197",
        lng: "71.7478"
      }
    },
    "phone": "1-477-935-8478 x6430",
    "website": "ola.org",
    company: {
      name: "Considine-Lockman",
      catchPhrase: "Synchronised bottom-line interface",
      bs: "e-enable innovative applications"
    }
  },
  {
    id: 7,
    name: "Kurtis Weissnat",
    username: "Elwyn.Skiles",
    email: "Telly.Hoeger@billy.biz",
    address: {
      street: "Rex Trail",
      suite: "Suite 280",
      city: "Howemouth",
      zipcode: "58804-1099",
      geo: {
        lat: "24.8918",
        lng: "21.8984"
      }
    },
    "phone": "210.067.6132",
    "website": "elvis.io",
    company: {
      name: "Johns Group",
      catchPhrase: "Configurable multimedia task-force",
      bs: "generate enterprise e-tailers"
    }
  },
  {
    id: 8,
    name: "Nicholas Runolfsdottir V",
    username: "Maxime_Nienow",
    email: "Sherwood@rosamond.me",
    address: {
      street: "Ellsworth Summit",
      suite: "Suite 729",
      city: "Aliyaview",
      zipcode: "45169",
      geo: {
        lat: "-14.3990",
        lng: "-120.7677"
      }
    },
    "phone": "586.493.6943 x140",
    "website": "jacynthe.com",
    company: {
      name: "Abernathy Group",
      catchPhrase: "Implemented secondary concept",
      bs: "e-enable extensible e-tailers"
    }
  },
  {
    id: 9,
    name: "Glenna Reichert",
    username: "Delphine",
    email: "Chaim_McDermott@dana.io",
    address: {
      street: "Dayna Park",
      suite: "Suite 449",
      city: "Bartholomebury",
      zipcode: "76495-3109",
      geo: {
        lat: "24.6463",
        lng: "-168.8889"
      }
    },
    "phone": "(775)976-6794 x41206",
    "website": "conrad.com",
    company: {
      name: "Yost and Sons",
      catchPhrase: "Switchable contextually-based project",
      bs: "aggregate real-time technologies"
    }
  },
  {
    id: 10,
    name: "Clementina DuBuque",
    username: "Moriah.Stanton",
    email: "Rey.Padberg@karina.biz",
    address: {
      street: "Kattie Turnpike",
      suite: "Suite 198",
      city: "Lebsackbury",
      zipcode: "31428-2261",
      geo: {
        lat: "-38.2386",
        lng: "57.2232"
      }
    },
    phone: "024-648-3804",
    website: "ambrose.net",
    company: {
      name: "Hoeger LLC",
      catchPhrase: "Centralized empowering task-force",
      bs: "target end-to-end models"
    }
  }
]
const CustomEditor = {
  name: 'CustomEditor',
  template: '#editor-template',
  extends: BaseEditorComponent,
  data: function() {
    return {
      // We'll need to define properties in our data object,
      // corresponding to all of the data being injected from
      // the BaseEditorComponent class, which are:
      // - hotInstance (instance of Handsontable)
      // - row (row index)
      // - col (column index)
      // - prop (column property name)
      // - TD (the HTML cell element)
      // - originalValue (cell value passed to the editor)
      // - cellProperties (the cellProperties object for the edited cell)
      hotInstance: null,
      TD: null,
      row: null,
      col: null,
      prop: null,
      originalValue: null,
      value: '',
      cellProperties: null,
      isVisible: false,
      style: {
        position: 'absolute',
        padding: '15px',
        background: '#fff',
        zIndex: 999,
        border: '1px solid #000'
      }
    }
  },
  methods: {
    stopMousedownPropagation: function(e) {
      e.stopPropagation();
    },
    prepare: function(row, col, prop, td, originalValue, cellProperties) {
      // We'll need to call the `prepare` method from
      // the `BaseEditorComponent` class, as it provides
      // the component with the information needed to use the editor
      // (hotInstance, row, col, prop, TD, originalValue, cellProperties)
      BaseEditorComponent.options.methods.prepare.call(this, row, col, prop, td, originalValue, cellProperties);

      if (!document.body.contains(this.$el)) {
        document.body.appendChild(this.$el);
      }

      const tdPosition = td.getBoundingClientRect();

      // As the `prepare` method is triggered after selecting
      // any cell, we're updating the styles for the editor element,
      // so it shows up in the correct position.
      this.style.left = tdPosition.left + window.pageXOffset + 'px';
      this.style.top = tdPosition.top + window.pageYOffset + 'px';
    },
    setLowerCase: function() {
      this.setValue(this.value.toLowerCase());
      this.finishEditing();
    },
    setUpperCase: function() {
      this.setValue(this.value.toUpperCase());
      this.finishEditing();
    },
    open: function() {
      this.isVisible = true;
    },
    close: function() {
      this.isVisible = false;
    },
    setValue: function(value) {
      this.value = value;
    },
    getValue: function() {
      return this.value;
    }
  }
};
export default {
  name: "PeoplesTable",
  data: function() {
    return {
      dataObject: dataObject,
      hotSettings: {
        data: dataObject,
        licenseKey: 'non-commercial-and-evaluation',
        rowHeaders: true,
        columns: [
          {
            data: 'id',
            type: 'numeric',
            width: 40
          },
          {
            data: 'name',
            type: 'text'
          },
          {
            data: 'username',
            type: 'text'
          },
          {
            data: 'address',
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
          {
            data: 'company',
            type: 'text'
          }
        ],
        colHeaders: [
          'ID',
          'Name',
          'Username',
          'Address',
          'phone',
          'website',
          'Company'
        ]
      },
    }
  },
  components: {
    HotTable,
    HotColumn
  },
  computed: {
    getApiData: function() {
      return this.apiData;
    }
  },
  // mounted: function() {
  //   this.recieveData();
  // },
  methods: {
    recieveData: function() {
      // this.axios.get('https://jsonplaceholder.typicode.com/users').then((response) => {
      //   this.dataObject = response.data;
      //   console.log(this.dataObject);
      // })
      // console.log(Handsontable.helper.createSpreadsheetData(10, 10))

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