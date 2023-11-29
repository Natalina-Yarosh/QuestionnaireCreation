<script setup>
    defineProps({
        currentStep: {
            type: Number,
            required: true
        }
    })
</script>

<template>
    <div class="step" >
            <div class="main-form-body">
                <TheStep :currentStep="currentStep"/>
                <div class="main-form-submit">
                    <div class="submit-svg">
                        <img :src="stepFour.imgPath" :alt="stepFour.title">
                    </div>
                    <h3 class="step-title">{{ stepFour.title }}</h3>
                    <p class="step-text">{{ stepFour.text }}</p>
                    <TheButton textInfo="Submit" class="auto" />
                </div>
            </div>
            <div class="main-form-btns">
                <TheButton textInfo="Previous step" class="right previous-btn" @click="$emit('decreaseStep')"/>
            </div>
        </div> 
</template>

<script>
import TheStep from './TheStepNumber.vue';
import TheButton from './TheButton.vue';

export default {
    components: {TheStep, TheButton},
    data(){
        return{
            stepFour:{
                imgPath: '/assets/theForm/3.svg',
                title: 'Submit your quote request',
                text:'Please review all the information you previously typed in the past steps, and if all is okay, submit your message to receive a project quote in 24 - 48 hours.',
                id: 'submitStep'
            },
        }
    },
};
</script>