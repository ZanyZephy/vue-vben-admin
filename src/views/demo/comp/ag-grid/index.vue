<template>
  <!-- The AG Grid component -->
  <ag-grid-vue
    :rowData="rowData"
    :columnDefs="colDefs"
    style="height: 500px"
    class="ag-theme-quartz"
    :enableRangeSelection="true"
    :enableRangeHandle="true"
    :enableFillHandle="true"
  />
</template>

<script setup>
  import { ref } from 'vue';
  import { AgGridVue } from 'ag-grid-vue3'; // Vue Data Grid Component
  import 'ag-grid-community/styles/ag-grid.css'; // Mandatory CSS required by the grid
  import 'ag-grid-community/styles/ag-theme-quartz.css';
  import 'ag-grid-enterprise';
  // Optional Theme applied to the grid
  const rowData = ref([
    { make: 'Tesla', model: 'Model Y', price: 64950, electric: true },
    { make: 'Ford', model: 'F-Series', price: 33850, electric: false },
    { make: 'Toyota', model: 'Corolla', price: 29600, electric: false },
  ]);

  // Column Definitions: Defines the columns to be displayed.
  const colDefs = ref([
    { field: 'make', editable: true },
    { field: 'model', editable: true },
    { field: 'price', editable: true },
    { field: 'electric', editable: true },
  ]);
</script>
