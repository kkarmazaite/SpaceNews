<template>
      <div id="content-container">
        <main>
            <h1 id="content-title">Articles</h1>
            <div id="article-list">
                <Article v-for="article in articles" :key="article.id" :article="article" />
            </div>
        </main>
    </div>
</template>

<script>

import AppHeader from "../../components/AppHeader"
import Article from "../../components/Article"

export default {
    components: {
        AppHeader,
        Article
    },
    data() {
        return {
        articles: []
        };
    },
    async fetch() {
        this.articles = await fetch("https://api.spaceflightnewsapi.net/v3/articles").then(articles => articles.json());
    },
}
</script>

<style scope>
    #content-background{
        width: 80vw !important;
    }
    #article-list{
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        gap: 35px;
    }

</style>