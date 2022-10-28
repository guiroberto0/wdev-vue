<template>
<main>
  <section class="container">
    <h1>Contato</h1>
      <section class="contacts">
        <div class="contact" v-for="(contactss, index) in contact" :key="index">
          <div class="contact-title">{{ contactss.title }}</div>
          <a :href="contactss.link" target="blank"> {{ contactss.label }}</a>
        </div>
      </section>
  </section>
</main>
</template>

<script>
import api from '@/services/api';
export default {
    name: "Contato-v",
    data () {
      return {
        contact: [],
      }
    },

    mounted () {
      api.get('/contacts.json').then(res =>{
        this.contact = res.data;
      });
    },
}
</script>

<style scoped>
  main {
    align-items: center;
  }

  .contact {
    margin: 0 0 30px 0;
  }

  .contact-title {
    font-weight: 600;
  }

  .contact a {
    color: var(--color-text-dark);
  }

</style>