<template>
    <h2 class="main-form-title">Get a project quote</h2>
    <p class="main-form-text">Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</p>
    <form class="main-form" @submit.prevent="submitForm">
        <StepOne  v-if="currentStep === 1" :currentStep="currentStep" @increase-step="handleStepUpdate" @update-form="handleUpdate" />
        <StepTwo  v-if="currentStep === 2" :currentStep="currentStep" @increase-step="handleStepUpdate" @decrease-step="previousStep" @update-form="handleUpdate"/>
        <StepThree v-if="currentStep === 3" :currentStep="currentStep" @increase-step="handleStepUpdate" @decrease-step="previousStep" @update-form="handleUpdate"/>
        <StepFour  v-if="currentStep === 4" :currentStep="currentStep" @decrease-step="previousStep" />
    </form>
</template>

<script>
import TheStep from './TheStepNumber.vue';
import TheButton from './TheButton.vue';
import TheInput from './TheInput.vue';

import StepOne from './StepOne.vue';
import StepTwo from './StepTwo.vue';
import StepThree from './StepThree.vue';
import StepFour from './StepFour.vue';


export default {
    components: {TheButton, TheInput, TheStep, StepOne, StepTwo, StepThree, StepFour},
    data(){
      return{
        currentStep: 1,
        formData:{
            userName: '',
            userEmail: '',
            userPhone: '',
            userCompany:'',
            userDevelopment: false,
            userWebDesign: false,
            userMarketing: false,
            userOther: false,
            userFirstPrice: false,
            userSecondPrice: false,
            userThirdPrice : false, 
            userFourthPrice: false
        },
      }
    },
     methods:{
        handleStepUpdate() {
            this.currentStep++;
        },
        previousStep(){
            this.currentStep--;
        },
        submitForm() {
            localStorage.setItem('formData', JSON.stringify(this.formData));
        },
        handleUpdate(updatedValue) {
            this.formData = { ...this.formData, ...updatedValue };
        },
    } 
}
</script>

<style scoped>
.main-form-title {
    color: var(--neutral-800, #170F49);
    text-align: center;
    font-size: 34px;
    font-weight: 700;
    line-height: 46px;
    letter-spacing: 1px;
    margin-bottom: 12px;
}

.main-form-text {
    max-width: 517px;
    margin: 0 auto 54px;
    color: var(--neutral-600, #6F6C90);
    text-align: center;
    font-size: 18px;
    font-weight: 400;
    line-height: 30px;
}

@media(max-width:767px){
  .main-form-title{
      font-size: 28px;
      line-height: 35px;
      letter-spacing: 0;
  }
  .main-form-text[data-v-9bb7623f] {
      max-width: 100%;
      font-size: 16px;
      line-height: 24px;
  }
}
</style>