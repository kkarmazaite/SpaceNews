<template>
        <main>
            <h1 id="content-title">{{this.article.title}}</h1>
            <div id="article-info">
                <small>{{this.article.newsSite}} - {{this.published}}</small>
                <img :src="article.imageUrl" alt="">
                <p>{{this.article.summary}}</p>
                <button @click="goToFullArticle()">Read full article</button>
            </div>
        </main>
</template>

<script>
export default {
    head(){
        return{
            title:this.article.title,
            meta:[
                {
                    hid: 'description',
                    name: 'description',
                    content: this.article.title
                }
            ]
        }
    },
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

<style scope>
    #content{
        padding: 5vh 10vw;
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