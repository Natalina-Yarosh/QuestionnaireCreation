<template>
  <header>
   <div class="container">
      <TheHeader />
    </div>
  </header>
  <section class="banner">
    <div class="container">
      <TheBanner />
    </div>
  </section>
  <!--
  <div>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </div>
  <main>
    <TheWelcome />
  </main>  -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import TheHeader from './components/TheHeader.vue'
import TheBanner from './components/TheBanner.vue'
export default {
    components: {TheHeader, TheBanner},
    data(){
      return{

      }
    }
}
</script>

<style scoped>
header{
  padding: 32px 0;
  position: fixed;
  width: 100%;
  left: 0;
  top: 0;
}
header .container{
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.banner{
  height: 100vh;
  display: grid;
  align-items: center;
  justify-content: center;
  position: relative;
  padding: 130px 0;
  text-align: center;
}
.banner .container{
  max-width: 680px;
}
</style>
