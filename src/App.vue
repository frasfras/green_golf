<template>
  <div id="app">
   
     <div class="input m-4">
  
  </div>
  <div class="input m-4">
  
    
      <toggle-button
        class="mb-3"
        v-model="fairw"
        :value="false"
        color="#AE41A7"
        :sync="true"
        :width="65"
        :labels="{checked: 'GPU', unchecked: 'CPU'}"
      />
  </div><div class="input m-4">
  
  </div>
   <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">Plan</router-link>
    </nav>
    <router-view/>
  </div>
</template>
<script>


/*import { ToggleButton } from 'vue-js-toggle-button';*/

export default {
  name: 'App',
  components: {
   
    
  },
   data() {
    return {
      gpu: false,
      fairw: false,
      cpu: false,
      green: false
    };
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
