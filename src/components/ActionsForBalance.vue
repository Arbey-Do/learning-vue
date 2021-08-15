<template>
    <button @click="this.$emit('modifyBalance')">{{ textButton }}</button>
</template>

<script>
    export default {
        props: {
            textButton: String
        }
    }
</script>

<style>
    
</style>