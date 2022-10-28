<template>
  <div id="app">
    <div>
      <NavBar />
      <router-view path="$router.key" />
      <FooterV />
    </div>
  </div>
</template>

<script>
//global style
import './style/global.css';
import NavBar from './components/NavBar.vue';
import FooterV from './components/FooterV.vue';
//components
export default {
  name: 'App',
  components: {
    NavBar,
    FooterV
},
  data(){
    return{
    }
  },
  methods:{
  }
}
</script>

<style>

</style>
