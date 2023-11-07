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

<script>

</script>


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
}
</style>