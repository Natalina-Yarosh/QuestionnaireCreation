<script setup>
    defineProps({
        currentStep: {
            type: Number,
            required: true
        }
    })
</script>

<template>
     <div class="main-body-steps">
        <div class="step-item active">
            <p>1</p>
        </div>
        <div :class="{'line': true, 'done':  currentStep >= 2}"></div>
        <div :class="{'step-item': true, 'active': currentStep >= 2}">
            <p>2</p>
        </div>
        <div :class="{'line': true, 'done': currentStep >= 3}"></div>
        <div :class="{'step-item': true, 'active': currentStep >= 3}">
            <p>3</p>
        </div>
        <div :class="{'line': true, 'done': currentStep === 4}"></div>
        <div :class="{'step-item': true, 'active': currentStep === 4}">
            <p>4</p>
        </div>
    </div>
</template>



<style scoped>
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
</style>