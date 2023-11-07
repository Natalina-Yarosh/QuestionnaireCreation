<template>
    <p class="subtitle">Cloneables FOR WEBFLOW</p>
    <h1 class="title">Multi-step Form Webflow Cloneable Template</h1>
    <p class="text">Want to receive a monthly email in your inbox with awesome free Webflow cloneables, resources and more? Please submit your email below.</p>
    <form class="form">
        <div class="form-group form-top">
            <TheInput :inputType="typeInput" :inputPlaceholder="placeholderInput"/>
            <TheButton :textInfo="textButton"/>
        </div>
        <div class="form-group form-bottom">
            <input type="checkbox" id="agreement">
            <div class="custom-checkbox">
                <img src="/assets/agree.svg" alt="It's 100% free and we will never send more than one email per month">
            </div>
            <label for="agreement">It's <span>100% free</span>  and we will never send more than one email per month</label>
        </div>
    </form>
    <article class="article">
        <h3 class="article__title">Multi Step Form - Step 1</h3>
        <button class="btn-secondary">Preview Cloneable</button>
    </article>
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
        placeholderInput: 'Enter your email'
      }
    }
}
</script>

<style scoped>

.subtitle{
    color: var(--primary-color-1, #4A3AFF);
    font-size: 16px;
    font-weight: 500;
    line-height: 18px; 
    letter-spacing: 3.84px;
    text-transform: uppercase;
    margin-bottom: 12px;
}

.title{
    color: var(--neutral-800, #170F49);
    font-size: 50px;
    font-weight: 700;
    line-height: 62px; 
    margin-bottom: 13px;
}

.text{
    color: var(--neutral-600, #6F6C90);
    font-size: 18px;
    font-weight: 400;
    line-height: 30px; 
    margin-bottom: 40px;
}
.article{
    position: absolute;
    left: 50%;
    bottom: 44px;
    max-width: 1242px;
    width: calc(100% - 30px);
    transform: translateX(-50%);
    border-radius: 18px;
    background: var(--neutral-100, #FFF);
    box-shadow: 0px 12px 24px 0px rgba(20, 20, 43, 0.04), 0px -2px 4px 0px rgba(20, 20, 43, 0.02), 0px 3px 14px 0px rgba(74, 58, 255, 0.03);
    padding: 27px 41px 30px 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.article__title{
    color: var(--neutral-800, #170F49);
    font-size: 24px;
    font-weight: 700;
    line-height: 35px; 
}

.btn-secondary{
    padding: 16px 28px 17px;
    border-radius: 50px;
    background: var(--secondary-color-1, #F3F1FF);  
    border: none;
    color: var(--primary-color-1, #4A3AFF);
    font-size: 16px;
    font-weight: 500;
    line-height: 18px; 
}
</style>