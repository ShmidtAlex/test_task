<template>
  <div class="people">
    <h3>Посетители</h3>
    <div class="table_block">
      <PeoplesTable />
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
      
    }
  };
</script>
<style scoped lang="less">
@media (min-width: 569px) {
  
  .people {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
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
      height: 77%;
      
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

</style>