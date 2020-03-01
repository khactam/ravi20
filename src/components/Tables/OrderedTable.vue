<template>
  <div>
    <md-table v-model="orders" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell class="md-table-cell-customized" md-label="Main course">{{item.main}}</md-table-cell>
        <md-table-cell class="md-table-cell-customized" md-label="Drink">{{item.drink}}</md-table-cell>
        <md-table-cell class="md-table-cell-customized" md-label="Total">{{item.price}}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "ordered-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      selected: [],
      orders: [
        {
          main: "Pho bo kho (8e)",
          drink: "Water (0e)",
          price: "8e",
        }
      ]
    };
  }
};
</script>
<style lang="scss">
.md-table-cell-customized{
  text-align: left!important;
}
</style>
