<template>
    <div class="step">
        <div class="main-form-body">
            <TheStep :currentStep="currentStep"/>
            <h3 class="step-title">{{ stepTwo.title }}</h3>
            <p class="step-text">{{ stepTwo.text }}</p>
            <div class="inputs inputs-servises">
                <div class="form-group" v-for="input in stepTwo.inputs" :key="input.id">
                    <TheInput :currentStep="currentStep" :id="input.id" :inputType="input.type" :name="input.name" @updateForm="handleUpdate"/>
                    <div class="form-group-body">
                        <label :for="input.id">
                            <div class="form-group-img">
                                <img :src="input.imgPath" :alt="input.label">
                            </div>
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
    props: ['currentStep'],
    data(){
        return{
            stepTwo:{
                title: 'Our services',
                text:'Please select which service you are interested in.',
                inputs:[
                    {
                        id: 'userDevelopment',
                        label: 'Development',
                        type: 'checkbox',
                        name: 'servises',
                        imgPath: '/assets/theForm/2-0.svg',
                    },
                    {
                        id: 'userWebDesign',
                        label: 'Web Design ',
                        type: 'checkbox',
                        name: 'servises',
                        imgPath: '/assets/theForm/2-1.svg',
                    },
                    {
                        id: 'userMarketing',
                        label: 'Marketing',
                        type: 'checkbox',
                        name: 'servises',
                        imgPath: '/assets/theForm/2-2.svg',
                    },
                    {
                        id: 'userOther',
                        label: 'Other',
                        type: 'checkbox',
                        name: 'servises',
                        imgPath: '/assets/theForm/2-3.svg',
                    }
                ],
                id: 'secondStep'
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