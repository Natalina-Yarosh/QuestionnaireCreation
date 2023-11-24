<template>
    <h2 class="main-form-title">Get a project quote</h2>
    <p class="main-form-text">Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</p>
    <form class="main-form" @submit.prevent="submitForm">
        <div class="step" v-if="currentStep === 1">
            <div class="main-form-body">
                <div class="main-body-steps">
                    <div class="step-item active">
                        <p>1</p>
                    </div>
                    <div class="line"></div>
                    <div class="step-item">
                        <p>2</p>
                    </div>
                    <div class="line"></div>
                    <div class="step-item">
                        <p>3</p>
                    </div>
                    <div class="line"></div>
                    <div class="step-item">
                        <p>4</p>
                    </div>
                </div>
                <h3 class="step-title">{{ stepOne.title }}</h3>
                <p class="step-text">{{ stepOne.text }}</p>
                <div class="inputs">
                    <div class="form-group" v-for="input in stepOne.inputs" :key="input.id">
                        <label :for="input.id">{{ input.label }}</label>
                        <div class="form-group-body">
                                <TheInput :currentStep="currentStep"  :id="input.id" :inputType="input.type" :inputPlaceholder="input.placeholder" @updateOne="handleStepOneUpdate" />
                            <div class="form-group-img">
                                <img :src="input.imgPath" :alt="input.label">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="main-form-btns">
                <TheButton textInfo="Next step" class="left" @click="nextStep"/>
            </div>
        </div>
        <div class="step" v-if="currentStep === 2">
            <div class="main-form-body">
                <div class="main-body-steps">
                    <div class="step-item active">
                        <p>1</p>
                    </div>
                    <div class="line done"></div>
                    <div class="step-item active">
                        <p>2</p>
                    </div>
                    <div class="line"></div>
                    <div class="step-item">
                        <p>3</p>
                    </div>
                    <div class="line"></div>
                    <div class="step-item">
                        <p>4</p>
                    </div>
                </div>
                <h3 class="step-title">{{ stepTwo.title }}</h3>
                <p class="step-text">{{ stepTwo.text }}</p>
                <div class="inputs inputs-servises">
                    <div class="form-group" v-for="input in stepTwo.inputs" :key="input.id">
                        <TheInput :currentStep="currentStep" :id="input.id" :inputType="input.type" @updateTwo="handleStepTwoUpdate" />
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
                <TheButton textInfo="Previous step" class="right previous-btn" @click="previousStep"/>
                <TheButton textInfo="Next step" class="left" @click="nextStep"/>
            </div>
        </div>
        <div class="step" v-if="currentStep === 3">
            <div class="main-form-body">
                <div class="main-body-steps">
                    <div class="step-item active">
                        <p>1</p>
                    </div>
                    <div class="line done"></div>
                    <div class="step-item active">
                        <p>2</p>
                    </div>
                    <div class="line done"></div>
                    <div class="step-item active">
                        <p>3</p>
                    </div>
                    <div class="line"></div>
                    <div class="step-item">
                        <p>4</p>
                    </div>
                </div>
                <h3 class="step-title">{{ stepThree.title }}</h3>
                <p class="step-text">{{ stepThree.text }}</p>
                <div class="inputs inputs-budget">
                    <div class="form-group" v-for="input in stepThree.inputs" :key="input.id">
                        <TheInput  :currentStep="currentStep" :id="input.id" :inputType="input.type" @updateThree="handleStepThreeUpdate"/>
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
                <TheButton textInfo="Previous step" class="right previous-btn" @click="previousStep"/>
                <TheButton textInfo="Next step" class="left" @click="nextStep"/>
            </div>
        </div>
        <div class="step" v-if="currentStep === 4">
            <div class="main-form-body">
                <div class="main-body-steps">
                    <div class="step-item active">
                        <p>1</p>
                    </div>
                    <div class="line done"></div>
                    <div class="step-item active">
                        <p>2</p>
                    </div>
                    <div class="line done"></div>
                    <div class="step-item active">
                        <p>3</p>
                    </div>
                    <div class="line done"></div>
                    <div class="step-item active">
                        <p>4</p>
                    </div>
                </div>
                <div class="main-form-submit">
                    <div class="submit-svg">
                        <img :src="stepSubmit.imgPath" :alt="stepSubmit.title">
                    </div>
                    <h3 class="step-title">{{ stepSubmit.title }}</h3>
                    <p class="step-text">{{ stepSubmit.text }}</p>
                    <TheButton textInfo="Submit" class="auto" type="submit"/>
                </div>
            </div>
            <div class="main-form-btns">
                <TheButton textInfo="Previous step" class="right previous-btn" @click="previousStep"/>
            </div>
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
        currentStep: 1,
        formData:{
            stepOne: {
                userName: '',
                userEmail: '',
                userPhone: '',
                userCompany:''
            },
            stepTwo: {
                userDevelopment: false,
                userWebDesign: false,
                userMarketing: false,
                userOther: false
            },
            stepThree:{
                userFirstPrice: false,
                userSecondPrice: false,
                userThirdPrice : false, 
                userFourthPrice: false
            }
        },
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
        stepTwo:{
            title: 'Our services',
            text:'Please select which service you are interested in.',
            inputs:[
                {
                    id: 'userDevelopment',
                    label: 'Development',
                    type: 'checkbox',
                    imgPath: '/assets/theForm/2-0.svg',
                },
                {
                    id: 'userWebDesign',
                    label: 'Web Design ',
                    type: 'checkbox',
                    imgPath: '/assets/theForm/2-1.svg',
                },
                {
                    id: 'userMarketing',
                    label: 'Marketing',
                    type: 'checkbox',
                    imgPath: '/assets/theForm/2-2.svg',
                },
                {
                    id: 'userOther',
                    label: 'Other',
                    type: 'checkbox',
                    imgPath: '/assets/theForm/2-3.svg',
                }
            ],
            id: 'secondStep'
        },
        stepThree:{
            title: 'What’s your project budget?',
            text:'Please select the project budget range you have in mind.',
            inputs:[
                {
                    id: 'userFirstPrice',
                    label: '$5.000 - $10.000',
                    type: 'radio',
                },
                {
                    id: 'userSecondPrice',
                    label: '$10.000 - $20.000',
                    type: 'radio',
                },
                {
                    id: 'userThirdPrice',
                    label: '$20.000 - $50.000',
                    type: 'radio',
                },
                {
                    id: 'userFourthPrice',
                    label: '$50.000 +',
                    type: 'radio',
                }
            ],
            id: 'thirdStep'
        },
        stepSubmit:{
            imgPath: '/assets/theForm/3.svg',
            title: 'Submit your quote request',
            text:'Please review all the information you previously typed in the past steps, and if all is okay, submit your message to receive a project quote in 24 - 48 hours.',
            id: 'submitStep'
        },
      }
    },
     methods:{
        nextStep() {
            this.currentStep++;
        },
        previousStep(){
            this.currentStep--;
        },
        submitForm() {
            localStorage.setItem('formData', JSON.stringify(this.formData));
        },
        handleStepOneUpdate(updatedValue) {
            this.formData.stepOne = { ...this.formData.stepOne, ...updatedValue };
        },
        handleStepTwoUpdate(updatedValue) {
            this.formData.stepTwo = { ...this.formData.stepTwo, ...updatedValue };
        },
        handleStepThreeUpdate(updatedValue) {
            this.formData.stepThree = { ...this.formData.stepThree, ...updatedValue };
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

.step {
    max-width: 696px;
    margin: 0 auto;
}

.main-form-body {
    border-radius: 31px;
    border: 1px solid var(--neutral-300, #EFF0F6);
    background: var(--neutral-100, #FFF);
    box-shadow: 0px 5px 16px 0px rgba(8, 15, 52, 0.06);
    overflow: hidden;
    margin-bottom: 31px;
    padding: 33px 55px 80px;
}
.main-body-steps {
    display: flex;
    column-gap: 18px;
    border-bottom: 1px solid #D9DBE9;
    padding: 0 18px 29px;
    margin-bottom: 65px;
    align-items: center;
}

.step-item.active p{
    background: var(--primary-color-1, #4A3AFF);
    color: var(--neutral-100, #FFF);
}

.step-item.active + .line::before{
    content: '';
    width: 50%;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
    background: var(--primary-color-1, #4A3AFF);
    border-radius: 40px;
}

.line::before{
    transition:  all .3s linear;
}

.line.done::before{
    width: 100% !important;
}

.step-item p{
    width: 34px;
    height: 34px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    background: var(--neutral-300, #EFF0F6);
    color: var(--neutral-600, #6F6C90);
    font-size: 16px;
    font-weight: 400;
    line-height: 1;
    transition: all .3s linear;
}

.line {
    height: 6px;
    width: 100%;
    border-radius: 40px;
    background: var(--neutral-300, #EFF0F6);
    position: relative;
}

.step-title {
    color: var(--neutral-800, #170F49);
    font-size: 24px;
    font-weight: 700;
    line-height: 35px;
    margin-bottom: 7px;
}

.step-text {
    color: var(--neutral-600, #6F6C90);
    font-size: 18px;
    line-height: 30px;
    margin-bottom: 39px;
}

.inputs {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-column-gap: 18px;
    grid-row-gap: 44px;
}

.form-group label {
    color: var(--neutral-800, #170F49);
    font-size: 18px;
    font-weight: 500;
    line-height: 20px;
    margin-bottom: 18px;
    display: block;
}

.form-group-body{
    position: relative;

}

.form-group-img {
    position: absolute;
    display: flex;
    right: 19px;
    top: 50%;
    transform: translateY(-50%);
}

.main-form-btns{
    display: flex;
    justify-content: space-between;
}

.btn.left{
    margin-left: auto;
}

.form-group-body label{ 
    transition: border .3s linear;
}

.inputs-servises .form-group-body label:hover{
    border: 2px solid var(--primary-color-1, #4A3AFF);
}
.inputs-servises .form-group-body label,
.inputs-budget .form-group-body label{
    display: flex;
    align-items: center;
    column-gap: 12px;
    margin: 0;
}

.inputs-servises .form-group-body label,
.inputs-budget .form-group-body label{
    padding: 23px;
    border: 2px solid transparent;
    background: var(--neutral-100, #FFF);
    box-shadow: 0px 4px 10px 0px rgba(31, 37, 89, 0.07), 0px 2px 11px 0px rgba(69, 65, 164, 0.06);
    border-radius: 16px;
}
.inputs-servises .form-group-img{
    border-radius: 50%;
    position: relative;
    right: 0;
    top: 0;
    transform: none;
    width: 66px;
    height: 66px;
    background: rgba(74, 58, 255, .15);
}

.inputs-servises .form-group-img img{
    width: 100%;
    height: 100%;
    object-fit: none;
}

input[type='checkbox']:checked  + div label,
input[type='radio']:checked  + div label{
    border: 2px solid var(--primary-color-1, #4A3AFF);
}

.inputs.inputs-servises,
.inputs.inputs-budget {
    grid-column-gap: 28px;
    grid-row-gap: 28px;
}

.input-radio-custom {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    box-shadow: 0px -3px 7px 0px rgba(20, 20, 43, 0.08) inset;
    border: 1.2px solid var(--neutral-400, #D9DBE9);
}

input[type='radio']:checked  + div .input-radio-custom{
    border: 8px solid var(--primary-color-1, #4A3AFF);
}

.main-form-submit{
    text-align: center;
}

.submit-svg{
    max-width: 154px;
    margin: 0 auto 18px;
}

.submit-svg img{
    width: 100%;
    height: auto;
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
    .main-form-body{
        padding: 30px 20px;
    }
    .main-body-steps{
        column-gap: 10px;
        padding: 0 0 29px;
        margin-bottom: 25px;
    }
    .step-item p{
        width: 31px;
        height: 31px;
    }
    .step-title {
        font-size: 20px;
        line-height: 25px;
    }
    .step-text{
        font-size: 16px;
        line-height: 22px;
        margin-bottom: 30px;
    }

    .inputs,
    .inputs.inputs-servises{
        grid-template-columns: 1fr;
        grid-row-gap: 25px;
    }

    .form-group label {
        font-size: 16px;
        line-height: 16px;
        margin-bottom: 15px;
    }
    .main-form-btns{
        flex-wrap: wrap;
        row-gap: 15px;
    }
    .inputs-servises .form-group-body label, .inputs-budget .form-group-body label{
        margin: 0;
    }
    .inputs-servises .form-group-img {
        width: 50px;
        height: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .inputs-servises .form-group-img img {
        width: 50%;
        height: 50%;
    }
    .submit-svg{
        max-width: 120px;
    }
}

</style>