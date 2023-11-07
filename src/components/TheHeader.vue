<template>
    <a class="logo" href="#">
        <img :src="logo" alt="logo">
    </a>
    <TheButton :textInfo="textButton"/>
</template>

<script>
import TheButton from './TheButton.vue';
export default {
    components: {TheButton},
    data(){
        return{
            logo: '/assets/logo.svg',
            textButton: 'Clone now'
        }
    }
}
</script>


<style scoped>
.logo{
    display: flex;
    max-width: 304px;
}

.logo image{
    width: 100%;
    object-fit: cover;
    object-position: center;
    height: 100%;
}
</style>