<template>
   <div class="footer-info">
    <a class="logo" href="#">
        <img :src="logo" alt="logo">
    </a>
    <p class="footer-text">Copyright © BRIX Templates | All Rights Reserved</p>
   </div>
    <form class="form">
        <p class="form-text">Subscribe to receive free Webflow cloneables every month.</p>
        <div class="form-group form-top">
            <TheInput :inputType="typeInput" :inputPlaceholder="placeholderInput"/>
            <TheButton :textInfo="textButton"/>
        </div>
    </form>
</template>

<script>
import TheButton from './TheButton.vue';
import TheInput from './TheInput.vue';

export default {
    components: {TheButton, TheInput},
    data(){
      return{
        textButton: 'Subscribe',
        typeInput: 'text',
        placeholderInput: 'Enter your email',
        logo: '/assets/logo.svg',
      }
    }
}
</script>

<style scoped>


footer .logo{
    max-width: 263px;
    display: flex;
    margin-bottom: 17px;
}

footer .logo img{
    width: 100%;
    height: auto;
}

.footer-text {
    color: var(--neutral-600, #6F6C90);
    font-size: 18px;
    font-weight: 400;
    line-height: 30px;
}

.subtitle{
    color: var(--primary-color-1, #4A3AFF);
    font-size: 16px;
    font-weight: 500;
    line-height: 18px; 
    letter-spacing: 3.84px;
    text-transform: uppercase;
    margin-bottom: 12px;
}

.form-text {
    color: var(--neutral-800, #170F49);
    font-feature-settings: 'clig' off, 'liga' off;
    font-family: DM Sans;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 18px;
    margin-bottom: 21px;
}

footer .form{
    width: 100%;
    max-width: 509px;
}

footer .form-group.form-top{
    margin: 0;
}

.form-group.form-top{
    display: flex;
    max-width: 600px;
    margin: 0 auto 25px;
    position: relative;
}

.form-group.form-top input{
    padding: 25px 200px 30px 30px;
}

footer  .form-group.form-top button{
    position: absolute;
    right: 17px;
    top: 50%;
    transform: translate(0, -50%);
    padding: 14px 27px 14px 25px;
    font-size: 16px;
}

</style>