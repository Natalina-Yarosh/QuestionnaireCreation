<template>
    <article  v-for="article in articles" :key="article" :class="['article', article.classArticle]">
        <div class="article__info">
            <div class="article__logo">
                <img :src="article.logo" alt="logo">
            </div>
            <h2 class="article__title">{{ article.title }}</h2>
            <p class="article__text">{{ article.text }}</p>
            <TheButton :textInfo="article.textButton" :class="article.classButton"/>
        </div>
        <div class="article__image">
            <img :src="article.imageUrl" :alt="article.title">
        </div>
    </article>
</template>

<script>
import TheButton from './TheButton.vue';

export default {
    components: {TheButton},
  data(){
    return{
        articles:[
            {
                logo: '/assets/about/logo1.svg',
                title: 'Take a look at our amazing premium Webflow Templates',
                text: 'Also than having free Webflow cloneables, we create cutting-edge premium Webflow templates too.',
                textButton: 'Browse templates',
                imageUrl: '/assets/about/1.png',
                classButton:'btn-white',
                classArticle:'article-fiolet'
            },
            {
                logo: '/assets/about/logo2.svg',
                title:'Looking to design & develop an amazing Webflow website?',
                text:'If you want to get a hand from the amazing team behind BRIX Templates, get in touch with BRIX Agency today.',
                textButton: 'Get a quote',
                imageUrl: '/assets/about/2.png',
                classButton:'btn-red',
                classArticle:'article-white'
            }
        ]
    }
  }
}
</script>


<style scoped>
.article{
    padding: 82px 0 0;
    border-radius: 40px;
    overflow: hidden;
}

.article.article-fiolet{
    background: var(--secondary-gradient, linear-gradient(90deg, #4A3AFF 0%, #6D3AFF 100%));
}

article.article.article-white {
    border: 1px solid var(--neutral-300, #EFF0F6);
    background-color: #fff;
}

.article__info {
    padding: 0 55px;
}

.article__logo {
    margin-bottom: 15px;
}

.article__title {
    color: var(--neutral-100, #FFF);
    font-size: 24px;
    font-weight: 700;
    line-height: 35px;
    margin-bottom: 10px;
}

.article__text {
    color: var(--neutral-100, #FFF);
    font-size: 18px;
    line-height: 30px;
    margin-bottom: 28px;
}

article .btn {
    text-decoration-line: underline;
}

.article__image{
    margin-top: 10px;
    position: relative;
    aspect-ratio: 1/0.73;
    display: flex;
    bottom: -3px;
}

.article__image img{
    position: absolute;
    left: 0;
    bottom: 0;
    height: 100%;
    width: 100%;
    object-fit: cover;
}

.article-white .article__title{
    color: var(--neutral-800, #170F49);
}

.article-white .article__text{
    color: var(--neutral-600, #6F6C90);
}
</style>