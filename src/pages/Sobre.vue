<template>
<main>
  <section class="container">
    <h1>Sobre</h1>
    <div class="about" v-html="about"></div>
  </section>
</main>
</template>

<script>
import api from '@/services/api';
export default {
    name: "About-v",
    data () {
      return {
        about: '',
      }
    },

    mounted () {
      api.get('/about.json').then(res =>{
        this.about = res.data.about;
      });
    },
}
</script>

<style scoped>
  main {
    align-items: center;
  }

  .about {
    margin: 0 0 50px 0;
  }
</style>