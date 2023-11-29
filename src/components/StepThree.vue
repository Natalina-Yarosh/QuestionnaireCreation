<script setup>
    defineProps({
        currentStep: {
            type: Number,
            required: true
        }
    })
</script>

<template>
    <div class="step">
        <div class="main-form-body">
            <TheStep :currentStep="currentStep"/>
            <h3 class="step-title">{{ stepThree.title }}</h3>
            <p class="step-text">{{ stepThree.text }}</p>
            <div class="inputs inputs-budget">
                <div class="form-group" v-for="input in stepThree.inputs" :key="input.id">
                    <TheInput  :currentStep="currentStep" :id="input.id" :inputType="input.type" :name="input.name" @updateForm="handleUpdate"/>
                    <div class="form-group-body">
                        <label :for="input.id">
                            <div class="input-radio-custom"></div>
                            {{ input.label }}
                        </label>
                    </div>
                </div>
            </div>
        </div>
        <div class="main-form-btns">
            <TheButton textInfo="Previous step" class="right previous-btn" @click="$emit('decreaseStep')"/>
            <TheButton textInfo="Next step" class="left" @click="$emit('increaseStep')"/>
        </div>
    </div>
</template>

<script>
import TheStep from './TheStepNumber.vue';
import TheButton from './TheButton.vue';
import TheInput from './TheInput.vue';

export default {
    components: {TheStep, TheButton, TheInput},
    data(){
        return{
            stepThree:{
                title: 'What’s your project budget?',
                text:'Please select the project budget range you have in mind.',
                inputs:[
                    {
                        id: 'userFirstPrice',
                        label: '$5.000 - $10.000',
                        type: 'radio',
                        name:'budget'
                    },
                    {
                        id: 'userSecondPrice',
                        label: '$10.000 - $20.000',
                        type: 'radio',
                        name:'budget'
                    },
                    {
                        id: 'userThirdPrice',
                        label: '$20.000 - $50.000',
                        type: 'radio',
                        name:'budget'
                    },
                    {
                        id: 'userFourthPrice',
                        label: '$50.000 +',
                        type: 'radio',
                        name:'budget'
                    }
                ],
                id: 'thirdStep'
            },
        }
    },
    methods: {
        handleUpdate(updatedValue) {
            this.$emit('update-form', updatedValue);
        }
    }
};
</script>