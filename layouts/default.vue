<template>
    <div>
        <div id="content-background">
             <Nuxt />
        </div>
    </div>
</template>

<script>


export default {
  components: {
  }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    border: none;
    outline: none;
    box-sizing: border-box;
}
:root {
    --black: rgb(67, 67, 67);
    --grey: rgb(178, 178, 178);
    --purple: #b15bb1;
    --white: #f8f7f8;
  }
body {
    font-family: 'Roboto', sans-serif;
    font-size: 18px;
    color: var(--black);

    background-image: url("../assets/BacgroundImage.png");
    background-repeat: no-repeat, repeat;
    background-size: cover; 
    background-color: var(--purple);

    display: flex;
    justify-content: center;
    align-items: center;
    min-height:100vh;
   }
   #content-background{
    background-color: var(--white);
    width: 80vw;
    border-radius: 5px;
    -webkit-box-shadow: 0px 0px 50px 3px rgba(0,0,0,0.6); 
    box-shadow: 0px 0px 50px 3px rgba(0,0,0,0.6);
}
#content-background{
    background-color: var(--white);
    border-radius: 5px;
    -webkit-box-shadow: 0px 0px 50px 3px rgba(0,0,0,0.6); 
    box-shadow: 0px 0px 50px 3px rgba(0,0,0,0.6);
}
#content-container{
    padding: 30px;
}
main{
    width: 100%;
    padding-bottom: 60px;
}
#content-title{
    margin-bottom: 30px;
    color: var(--purple);
    text-transform: uppercase;
}
</style>