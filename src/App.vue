<template>

  <div class="main-form">
    <div class="container">
      <TheForm/>
    </div>
  </div>
 
 
  <!-- <div>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </div> -->
  <main>
    <TheWelcome />
  </main> 
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import TheForm from './components/TheForm.vue'
export default {
    components: {TheForm, TheWelcome},
    data(){
      return{
        
      }
    }
}
</script>

<style scoped>
.main-form {
  padding: 127px 0;
  background: var(--neutral-200, #F7F7FB);
}
</style>
