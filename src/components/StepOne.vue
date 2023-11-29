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
                <h3 class="step-title">{{ stepOne.title }}</h3>
                <p class="step-text">{{ stepOne.text }}</p>
                <div class="inputs">
                    <div class="form-group" v-for="input in stepOne.inputs" :key="input.id">
                        <label :for="input.id">{{ input.label }}</label>
                        <div class="form-group-body">
                                <TheInput :currentStep="currentStep"  :id="input.id" :inputType="input.type" :inputPlaceholder="input.placeholder"  @updateForm="handleUpdate"/>
                            <div class="form-group-img">
                                <img :src="input.imgPath" :alt="input.label">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="main-form-btns">
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
            stepOne:{
                title: 'Contact details',
                text:'Lorem ipsum dolor sit amet consectetur adipisc.',
                inputs:[
                    {
                        id: 'userName',
                        label: 'Name',
                        type: 'text',
                        placeholder: 'John Carter',
                        imgPath: '/assets/theForm/1-0.svg',
                    },
                    {
                        id: 'userEmail',
                        label: 'Email ',
                        type: 'email',
                        placeholder: 'Email address',
                        imgPath: '/assets/theForm/1-1.svg',
                    },
                    {
                        id: 'userPhone',
                        label: 'Phone Number',
                        type: 'tel:(123) 456 - 7890',
                        placeholder: '(123) 456 - 7890',
                        imgPath: '/assets/theForm/1-2.svg',
                    },
                    {
                        id: 'userCompany',
                        label: 'Company',
                        type: 'text',
                        placeholder: 'Company name',
                        imgPath: '/assets/theForm/1-3.svg',
                    }
                ],
                id: 'firstStep'
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