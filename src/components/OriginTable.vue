<template>
  <el-table
    :data="tableData"
    :default-sort = "{prop: 'date', order: 'descending'}"
    style="width: 100%">
    <el-table-column
      prop="date"
      label="Date"
      sortable
      width="180">
      <template slot-scope="scope">
        <p>Date: {{scope.row.date}}</p>
      </template>
    </el-table-column>
    <el-table-column
      prop="name"
      label="Name"
      width="180">
    </el-table-column>
    <el-table-column
      prop="address"
      label="Address"
      :formatter="formatter">
    </el-table-column>
  </el-table>
</template>
<script>
  export default {
    props: {
      tableData: Array,
      default: () => {}
    },
    methods: {
      formatter(row) {
        /*eslint no-console: ["error", { allow: ["warn", "error", "log"] }] */
        console.log(row)
        return row.address
      }
    }    
  }
</script>