<template>
      <div id="content-container">
        <main>
            <h1 id="content-title">Article</h1>
        </main>
    </div>
</template>

<script>
export default {
    data() {
        return {
        article: {}
        };
    },
    async fetch() {
        this.article = await fetch(`https://api.spaceflightnewsapi.net/v3/articles/${this.$route.params.id}`).then(article => article.json());
        console.log(this.article)
    },
}
</script>

<style>

</style>