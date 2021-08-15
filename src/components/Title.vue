<template>
  <h1>{{message}}</h1>
</template>

<script>
export default {
    name: 'Title',
    props: {
        message: String
    }
}
</script>

<style scoped>
    h1 {
        color: peru;
    }
</style>