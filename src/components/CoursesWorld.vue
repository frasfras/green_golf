<template>

  <div class="hello">
  <h1>{{ msg }}</h1>Manual Control
   <div class="input m-4">
  Teebox
      <toggle-button
        class="mb-3"
        v-model="gpu"
        :value="false"
        color="#AE41A7"
        :sync="true"
        :width="65"
        :labels="{checked: 'ON', unchecked: 'OFF'}"
      />
  Greens  <label></label>
  
      <toggle-button
        class="mb-3"
        v-model="cpu"
        :value="false"
        color="#AE41A7"
        :sync="true"
        :width="65"
        :labels="{checked: 'ON', unchecked: 'OFF'}"
      />
      </div>
  <div class="input m-4">
  Fairways
      <toggle-button
        class="mb-3"
        v-model="fairw"
        :value="false"
        color="#AE41A7"
        :sync="true"
        :width="65"
        :labels="{checked: 'GPU', unchecked: 'CPU'}"
      />
  </div>
   <table id="demo-table-id" class="table table-striped">
        <caption></caption>
        <thead>
          <tr>
            <th>Hole</th>
            <th>Fairway </th>
            <th>Greens</th>
            <th>Teebox</th>
            <th>Roughs</th>
          </tr>
        </thead>
        <tbody>
         <tr>
            <td><input type="checkbox" id="checkbox" v-model="checked">
            <label for="checkbox">{{ checked }}</label>- Disable if it WILL rain</td>
            <td><button type="button" class="btn btn-primary"> minute</button> </td>
            <td><button type="button" class="btn btn-success">  minutes</button> </td>
            <td><button type="button" class="btn btn-info">  minutes</button> </td>
            <td><button type="button" class="btn btn-info">  minutes</button> </td>
          </tr>
          <tr>
            <td>1  </td>
            <td> 10</td>
            <td>13</td>
            <td>8</td>
            <td>12</td>
          </tr>
          <tr>
            <td>2 </td>
            <td> 9</td>
            <td>13</td>
            <td>15</td>
            <td>12</td>
          </tr>
          <tr>
            <td>3 </td>
            <td> 12</td>
            <td>13</td>
            <td>8</td>
            <td>12</td>
          </tr>
          <tr>
            <td>4</td>
            <td> 10</td>
            <td>13</td>
            <td>15</td>
            <td>12</td>
          </tr>

          <tr>
            <td>5 </td>
            <td> 10</td>
            <td>10</td>
            <td>15</td>
            <td>12</td>
          </tr>
          <tr>
            <td>6 </td>
            <td> 10</td>
            <td>15</td>
            <td>8</td>
            <td>15</td>
          </tr>
          <tr>
            <td>7 </td>
            <td> 10</td>
            <td>15</td>
            <td>15</td>
            <td>12</td>
          </tr>
          <tr>
            <td>8 </td>
            <td> 11</td>
            <td>15</td>
            <td>15</td>
            <td>12</td>
          </tr>
          <tr>
            <td>9 </td>
            <td> 8</td>
            <td>15</td>
            <td>15</td>
            <td>12</td>
          </tr>
          <tr class="info">
            <td colspan="4"></td>
            <td>
              <b></b>
            </td>
          </tr>
        </tbody>
      </table>
   
    
    
  </div>
</template>

<script>
import { ToggleButton } from 'vue-js-toggle-button';
import axios from "axios";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: {
    ToggleButton
  },
   data() {
    return {
      gpu: false,
      fairw: false,
      cpu: false,
      green: false,
      courses: null,
    };
  },
  created: function() {
      axios
        .get("https://mocki.io/v1/69bd11f5-7c1d-4637-8a20-07acbd823cf1")
        .then (res => { this.courses = res.data;});
  }
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
