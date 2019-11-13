<template>
  <el-table
    :data="tableData"
    :default-sort = "{prop: 'date', order: 'descending'}"
    style="width: 100%">
    <el-table-column
      v-for="column in haederData"
      :key="column.label"
      :prop="column.key"
      :label="column.label"
      sortable
      width="180">
      <template v-slot="scope">
        <slot :name="column.key" :data="scope.row[column.key]">
          {{scope.row[column.key]}}
        </slot>
      </template>
    </el-table-column>
  </el-table>
</template>
<script>
  export default {
    props: {
      tableData: Array,
      default: () => {}
    },
    data() {
      return {
        haederData: [{
          key: "date",
          label: "Date",
          render: (data) => {
            return <h3>${data} 템프릿테스트 </h3>;
          }
        }, {
          key: "name",
          label: "Name"
        }, {
          key: "address",
          label: "Address"
        }]
      }
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