<script setup>
    defineProps({
        textInfo: {
            type: String,
            required: true
        }
    })
</script>

<template>
    <button class="btn">{{ textInfo }}</button>
</template>

<style scoped>
.btn{
    border-radius: 56px;
    background: var(--primary-color-1, #4A3AFF);
    box-shadow: 0px 3px 12px 0px rgba(74, 58, 255, 0.18);
    padding: 20px 40px 21px 40px;
    color: var(--neutral-100, #FFF);
    font-size: 18px;
    font-weight: 700;
    line-height: 20px; 
    border: none;
    cursor: pointer;
    transition: all .3s linear;
}

.btn:hover{
    box-shadow: 0px 0px 20px 15px rgba(74, 58, 255, 0.18);
}

.btn-white {
    border-radius: 56px;
    background: var(--neutral-100, #FFF);
    box-shadow: 0px 3px 12px 0px rgba(20, 20, 43, 0.10);
color: var(--primary-color-1, #4A3AFF);
}

.previous-btn{
    border-radius: 66px;
    border: 1px solid var(--primary-color-1, #4A3AFF);
    color: var(--primary-color-1, #4A3AFF);
    background: transparent;
    font-weight: 400;
    box-shadow: none;
}

.previous-btn:hover{
    box-shadow: 0px 3px 20px 15px rgba(20, 20, 43, 0.10);
}

@media(max-width:767px){
    .btn{
        width: 100%;
        font-size: 16px;
        line-height: 18px;
    }
}
</style>