<template>
   
    <h2 class="main-form-title">Get a project quote</h2>
    <p class="main-form-text">Please fill the form below to receive a quote for your project. Feel free to add as much detail as needed.</p>
    
    <div class="step" v-for="step in steps" :key="step.id">
        <div class="main-form-body">
            <div class="main-body-steps">
                <div class="step-item">
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
            <h3 class="step-title">{{ step.title }}</h3>
            <p class="step-text">{{ step.text }}</p>
            <div class="inputs">
                <div class="form-group" v-for="input in step.inputs" :key="input.id">
                    <label :for="input.id">{{ input.label }}</label>
                    <div class="form-group-body">
                        <TheInput :id="input.id" :inputType="input.type" :inputPlaceholder="input.placeholder"/>
                        <!-- <input :id="input.id" :type="input.type" :placeholder="input.placeholder"/> -->
                        <div class="form-group-img">
                            <img :src="input.imgPath" :alt="input.label">
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="main-form-btns" v-for="btn in step.buttons" :key="btn">
            <TheButton :textInfo="btn.textButton" class="left"/>
        </div>
    </div>
    <!-- <form class="form">
        <div class="form-group form-top">
            <TheInput :inputType="typeInput" :inputPlaceholder="placeholderInput"/>
            <TheButton :textInfo="textButton"/>
        </div>
    </form> -->

</template>

<script>
import TheButton from './TheButton.vue';
import TheInput from './TheInput.vue';

export default {
    components: {TheButton, TheInput},
    data(){
      return{
        steps:[
            {
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
                buttons: [
                    {
                        textButton: 'Next step',
                    }
                ],
                id: 'firstStep'
            }
        ],
      }
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
}

.line {
    height: 6px;
    width: 100%;
    border-radius: 40px;
    background: var(--neutral-300, #EFF0F6);
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
</style>