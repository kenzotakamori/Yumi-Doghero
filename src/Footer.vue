<template>
    <footer>
        <div class="row">
            <a v-bind:href="instagramUrl" target="_blank">
                <i class="fab fa-instagram"></i>
            </a>
            <a v-bind:href="dogheroUrl" target="_blank">
                <i class="fas fa-dog"></i>
            </a>
            <a v-bind:href="whatsappUrl" target="_blank">
                <i class="fab fa-whatsapp"></i>
            </a>
        </div>
        <div class="row">
            Vai viajar? Deixe seu dog comigo!
        </div>
    </footer>
</template>

<script>
export default {
    data() {
        return {
            instagramUrl: "https://www.instagram.com/yumi.doghero",
            dogheroUrl: "https://www.doghero.com.br/heroi/113692",
            whatsappUrl: "https://api.whatsapp.com/send?phone=5512991201231"
        }
    }
}
</script>

<style>
    footer {
        background-color: red;
        height: 80px;
        line-height: 40px;
        text-align: center;
        color: white;
        bottom: 0;
        width: 100%;
    }

    footer a {
        text-decoration: none;
        color: white;
        font-size: 30px;
    }
</style>