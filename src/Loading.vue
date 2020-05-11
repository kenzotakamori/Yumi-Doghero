<template>
    <i class="fas fa-bone"></i>
</template>

<style>
    .fa-bone {
        animation:spin 1s linear infinite;
    }

    @-moz-keyframes spin { 100% { -moz-transform: rotate(360deg); } }
    @-webkit-keyframes spin { 100% { -webkit-transform: rotate(360deg); } }
    @keyframes spin { 100% { -webkit-transform: rotate(360deg); transform:rotate(360deg); } }
</style>