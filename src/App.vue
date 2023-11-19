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
  <div class="main-form">
    <div class="container">
      <TheForm/>
    </div>
  </div>
  <div class="footer-wrap-img"> 
    <div class="about">
    <div class="container">
      <About />
    </div>
  </div>
  <footer>
    <div class="container">
      <TheFooter/>
    </div>
  </footer>
  </div>
 
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
import About from './components/About.vue'
import TheFooter from './components/TheFooter.vue'
import TheForm from './components/TheForm.vue'
export default {
    components: {TheHeader, TheBanner, About, TheFooter, TheForm},
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
  background: var(--neutral-100, #FFF);
  z-index: 2;
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
  overflow: hidden;
}
.banner .container{
  max-width: 680px;
}

.banner::before{
  content: '';
  width: 788px;
  height: 788px;
  display: block;
  position: absolute;
  left: 0;
  bottom: 0;
  background-image: url(/public/assets/img.png);
  transform: translate(-42%, 31%);
  z-index: -1;
}
.about {
  padding: 175px 0px 84px;
  position: relative;
  overflow: hidden;
}

.about .container{
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 30px;
}

.footer-wrap-img{
  position: relative;
  overflow: hidden;
}
.footer-wrap-img::before{
  content: '';
  width: 788px;
  height: 788px;
  display: block;
  position: absolute;
  right: 0;
  bottom: 0;
  background-image: url(/public/assets/img.png);
  transform: translate(42%, -18%);
  z-index: -1;
}

footer{
  padding: 8px 0 58px;
}

footer .container{
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.main-form {
  padding: 127px 0;
  background: var(--neutral-200, #F7F7FB);
}
</style>
