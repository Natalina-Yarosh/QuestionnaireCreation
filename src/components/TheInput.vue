<script setup>
    defineProps({
        id: {
            type: String,
            required: true
        },
        inputType: {
            type: String,
            required: true
        },
        inputPlaceholder: {
            type: String,
            required: false
        },
        currentStep: {
            type: Number,
            required: true
        },
        name: {
            type: String,
            required: false
        },
    })
</script>

<template>
     <input :type="inputType" :id="id" :name="name" :placeholder="inputPlaceholder"  v-model="inputValue"  @change="handleUpdateForm"> 
</template>

<script>
export default {
    props: ['id', 'inputType', 'inputPlaceholder', 'currentStep', 'name'],
    emits: ['updateForm'],
    data() {
        return {
            inputValue: ''
        };
    },
    methods: {
        handleUpdateForm() {
            this.$emit('updateForm', { [this.id]: this.inputValue });
        }
    }
};
</script>

<style scoped> 
input{
    transition: all .3s linear;
}
input[type=text], 
input[type=email],
input[type^='tel']{
    border-radius: 60px;
    border: 1px solid var(--neutral-300, #EFF0F6);
    background: var(--neutral-100, #FFF);
    box-shadow: 0px 8px 25px 0px rgba(13, 10, 44, 0.06);
    width: 100%;
    padding: 25px 30px 32px;
    color: var(--neutral-600, #6F6C90);
    font-size: 18px;
    font-weight: 400;
    line-height: 20px; 
}
input::placeholder{
    color: var(--neutral-600, #6F6C90);
    font-size: 18px;
    font-weight: 400;
    line-height: 20px; 
}
input:focus{
    border-color: var(--primary-color-1, #4A3AFF);
    outline: none;
}
input:hover{
    border-color: var(--primary-color-1, #4A3AFF);
}

.form-group-body input[type=text], 
.form-group-body  input[type=email],
.form-group-body input[type^='tel']{
    padding: 20px 50px 25px 20px;
}

.inputs-servises input,
.inputs-budget input{
    display: none;
}

@media(max-width:767px){
    input[type=text], 
    input[type=email],
    input[type^='tel']{
        padding: 16px 50px 16px 16px;
        font-size: 16px;
    }
    input::placeholder{
        font-size: 16px;
    }
}
</style>