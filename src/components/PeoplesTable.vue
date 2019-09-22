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
  </div>
</template>

<script>
import { HotTable, HotColumn } from '@handsontable/vue';
import Handsontable from 'handsontable';
export default {
  name: "PeoplesTable",
  data:  function() {
    return {
      hotData: Handsontable.helper.createSpreadsheetData(10, 7),
      secondColumnSettings: {
        title: 'Username'
      }
    }
  },
  components: {
    HotTable,
    HotColumn
  }
};
</script>

<style lang="less">
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
  
  // .wtSpreader {
  //   width: 100% !important;
  // }
</style>