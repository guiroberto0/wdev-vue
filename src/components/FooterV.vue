<template>
  <footer>
    <a class="socialLink" v-for="(socialLink, index) in socialLinks" :key="index" :href="socialLink.link" target="blank">
        <img :src="socialLink.icon" :alt="socialLink.label" :title="socialLink.label">
    </a>
  </footer>
</template>

<script>
import api from '@/services/api.js';

export default {
    name: "Footer-vue",
    data () {
        return {
            socialLinks: [],            
        }
    },
    mounted () {
        api.get('/social-links.json').then(response => {
            this.socialLinks = response.data;
        })
    },
}
</script>

<style scoped>
footer {
    background-color: var(--color-background-nav);
    width: 100%;
    height: 60px;
    display: flex;
    align-content: center;
    justify-content: center;
  /*  position: fixed;
    left: 0; bottom: 0;*/
}

.socialLink {
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid var(--color-text-light);
    border-radius: 50%;
    width: 40px;
    height: 40px;
    margin-top: 10px;
    margin-right: 20px ;
}

.socialLink img {
    width: 20px;
}

</style>