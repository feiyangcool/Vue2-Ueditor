<template>
  <div id="app">
    <div>
      <u-e :defaultMsg="defaultMsg" :config="config" id="uuee" ref="ue"></u-e>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import UE from './components/ue/index.vue'
export default {
  name: 'App',
  components: {
    UE
  },
  data(){
    return{
      config: {
        UEDITOR_HOME_URL: "/static/UE",
        initialFrameWidth: "100%",
        initialFrameHeight: 300
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
