<template>
  <CustomTable :tableData=tableData>
    <template v-slot:date="slotProps">테스트 {{slotProps.data}}</template>
  </CustomTable>
</template>

<script>
  import CustomTable from "./CustomTable";
  export default {
    components: { CustomTable },
    data() {
      return {
        tableData: [{
          date: '2016-05-03',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles'
        }, {
          date: '2016-05-02',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles'
        }, {
          date: '2016-05-04',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles'
        }, {
          date: '2016-05-01',
          name: 'Tom',
          address: 'No. 189, Grove St, Los Angeles'
        }]
      }
    },
    
  }
</script>
