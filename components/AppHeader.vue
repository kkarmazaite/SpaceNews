<template>
  <header>
    <div id="logo"><i class="fa-solid fa-rocket-launch"></i> <strong>Space</strong> News</div>
  </header>
</template>

<script>
export default {
    name: "AppHeader"

}
</script>

<style>
    header{
        padding: 20px 0;
        margin-bottom: 40px;
        border-bottom: 1px solid var(--grey);
    }
    #logo{
        font-size: 25px;
    }
    #logo strong{
        color: var(--purple);
    }
</style>