<template>
  <div class="data-view">
    <h1>Data view</h1>
    <data-cell :main-value="dataCellValue"/>
    <button @click="randomiseNumber()">Randomise</button>
  </div>
</template>

<script>
import DataCell from "@/components/DataCell.vue";

export default {
  name: "DataView",
  props: {
    msg: String
  },
  data() {
    return {
      dataCellValue: 45.66
    };
  },
  components: {
    DataCell
  },
  methods: {
    randomiseNumber() {
      this.dataCellValue = +(Math.random() * 100).toFixed(3);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
