<template>
    <div class="text-secondary" id="footer">Desarrollado por Sergio Suárez.<br> Código disponible en <a id="enlaceGithub" href="https://github.com/SergioSuaGar"><img src="../assets/github.png">GitHub.</a></div>
</template>

<script>
    export default {
        name: "Footer"
    }
</script>

<style scoped>
  #footer{
     padding-top: 50px;
     bottom: 0;
     width: 90%;
     height: 40px;
     text-align: center;
 }
    #enlaceGithub{
        color: #12B188;
    }
</style>