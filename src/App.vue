<template>
  <div class="main-form">
    <div class="container">
      <TheForm/>
    </div>
  </div>
</template>

<script>
import TheForm from './components/TheForm.vue'
export default {
  components: {TheForm},
}
</script>

<style scoped>
.main-form {
  padding: 127px 0;
  background: var(--neutral-200, #F7F7FB);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media(max-width:767px){
  .main-form {
    padding: 50px 0;
  }
}
</style>
