<template>
        <main>
            <h1 id="content-title">Articles</h1>
            <div id="article-list">
                <Article v-for="article in articles" :key="article.id" :article="article" />
            </div>
        </main>
</template>

<script>

import AppHeader from "../../components/AppHeader"
import Article from "../../components/Article"

export default {
    head(){
        return{
            title:'Articles',
            meta:[
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Articles'
                }
            ]
        }
    },
    components: {
        AppHeader,
        Article
    },
    data() {
        return {
        articles: []
        };
    },
    async created() {
        this.articles = await fetch("https://api.spaceflightnewsapi.net/v3/articles").then(articles => articles.json());
    },
}
</script>

<style scope>
    #content{
        padding: 5vh 10vw;
    }
    #article-list{
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        gap: 35px;
    }

</style>