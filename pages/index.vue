<template>

</template>

<script>

export default {
    head(){
        return{
            title:'Space News',
            meta:[
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Space news'
                }
            ]
        }
    },
    created() {
      this.$router.push('/login')
    }

}
</script>
