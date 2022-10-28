<template>
  <main>
    <div class="text-top">
        Videos novos todas as <b>Quinta</b> as <b>20h</b>!
    </div>
    <a href="https://youtube.com.br" target="blank">
        <img src="../assets/subscribe.svg" alt="subscribe" id="subscribe">
    </a>
    <div class="text-bottom">
        youtube.com.br
    </div>
  </main>
</template>

<script>
export default {
    name: "Home-page",
}
</script>

<style scoped>
main{
    background-color: var(--color-background-home) ;
    justify-content: center;
    align-items: center;
}

.text-top {
    color: var(--color-text-light);
    margin: 0 0 20px 0;
}

#subscribe {
    width: 300px;
}

.text-bottom {
    color: var(--color-text-light);
    margin: 20px 0 0 0; 
}

</style>