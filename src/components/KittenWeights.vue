<template>
   <div id="app">
    <line-chart :data="data" />

    <ul>
      <li v-for="(value, k) in weightDic" :key="k">
        {{ k }}
          <table>
          <tr v-for="(v2, k2) in value" :key="k2"><td> {{ k2 }} </td><td>{{ v2 }} </td></tr>
          </table>
        </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'KittenWeights',
  props: {
    weightDic: {},
    data: []
  },
    mounted() {
    axios({ method: "GET",
            url: "https://api.myjson.com/bins/busmh",
            }).then(result => {
        this.weightDic = result.data.kittens;
        
        this.data = [];
        for (var k in this.weightDic) {
          var l = {name: k, data: this.weightDic[k]};
          this.data.push(l);
        }
          

    }, error => {
        this.errors.push(error);
  });
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
