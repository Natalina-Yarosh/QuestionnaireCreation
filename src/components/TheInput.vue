<script setup>
defineProps({
  inputType: {
    type: String,
    required: true
  },
  inputPlaceholder: {
    type: String,
    required: true
  },
})
</script>

<template>
    <input :type="inputType" :placeholder="inputPlaceholder">
</template>

<style scoped> 
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
</style>