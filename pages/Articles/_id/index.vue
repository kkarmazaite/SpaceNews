<template>
      <div id="content-container">
        <main>
            <h1 id="content-title">{{this.article.title}}</h1>
            <div id="article-info">
                <small>{{this.article.newsSite}} - {{this.published}}</small>
                <img :src="article.imageUrl" alt="">
                <p>{{this.article.summary}}</p>
                <button @click="goToFullArticle()">Read full article</button>
            </div>
        </main>
    </div>
</template>

<script>
export default {
    data() {
        return {
        article: {},
        published: ""
        };
    },
    async created(){
        this.article = await fetch(`https://api.spaceflightnewsapi.net/v3/articles/${this.$route.params.id}`).then(article => article.json());

        this.published=this.article.publishedAt.slice(0, 10)


    },
    methods:{
        goToFullArticle(){
            window.open(this.article.url, '_blank').focus();
        }
    }
}
</script>

<style>
    #content-background{
        width: 80vw !important;
    }
    #article-info{
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    #article-info img{
        height: 400px;
        width: 100%;
        object-fit: cover;
    }
    #article-info button{
       background-color: var(--purple);
        color: var(--white);
        font-size: 20px;
        font-weight: bold;
        margin: 30px 0px;
        height: 40px;
        border-radius: 4px;
    }
    #article-info button:hover{
        cursor: pointer;
        filter: brightness(110%);
    }
</style>