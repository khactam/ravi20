<template>
  <div class="content">
    <div class="md-layout">
      <div class="md-layout-item md-medium-size-25 md-xsmall-size-25 md-size-25">
        <h3>Order</h3>
        <draggable :list="myArray1" group="people">
          <div v-for="(element, id) in  myArray1" :key="id">
            <stats-card data-background-color="green" @click.native="onOrderClick(id)">
              <template slot="header">
                <md-icon>store</md-icon>
              </template>
              <template slot="content">
                <span>Order title</span>
                <p class="category">{{element.name}}</p>
              </template>
              <template slot="footer">
                <div class="stats">
                  <b>Created</b>: Last 24 Hours <br>
                  <b>Moved</b>: Last 24 Hours
                </div>
              </template>
            </stats-card>
          </div>
        </draggable>
      </div>
      <div class="md-layout-item md-medium-size-25 md-xsmall-size-25 md-size-25">
        <h3>Kitchen</h3>
        <draggable :list="myArray2" group="people">
          <div v-for="(element, id) in myArray2" :key="id">
            <stats-card data-background-color="green">
              <template slot="header">
                <md-icon>store</md-icon>
              </template>
              <template slot="content">
                <span>Test</span>
                <p class="category">{{element.name}}</p>
              </template>
              <template slot="footer">
                <div class="stats">
                  <md-icon>date_range</md-icon>Last 24 Hours
                </div>
              </template>
            </stats-card>
          </div>
        </draggable>
      </div>
    </div>
  </div>
</template>

<script>
import {
  StatsCard,
  ChartCard,
  NavTabsCard,
  NavTabsTable,
  OrderedTable
} from "@/components";
import draggable from "vuedraggable";
export default {
  components: {
    StatsCard,
    ChartCard,
    NavTabsCard,
    NavTabsTable,
    OrderedTable,
    draggable
  },
  data() {
    return {
      myArray1: [
        {
          name: "Cac 1",
          id: 1
        },
        {
          name: "Cac 2",
          id: 2
        },
        {
          name: "Cac 3",
          id: 3
        },
        {
          name: "Cac 4",
          id: 4
        }
      ],
      myArray2: [
        {
          name: "Cac",
          id: 1
        },
        {
          name: "Cac",
          id: 2
        },
        {
          name: "Cac",
          id: 3
        },
        {
          name: "Cac",
          id: 4
        }
      ]
    };
  },
  methods: {
    onOrderClick(id) {
      console.log(id);
    }
  }
};
</script>
