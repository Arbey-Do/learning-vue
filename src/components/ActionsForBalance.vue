<template>
    <button @click="modifyBalance" :disabled="disabled">{{ textButton }}</button>
</template>

<script>
    export default {
        data() {
            return {}
        },
        props: {
            textButton: String,
            disabled: {
                type: Boolean,
                default: false
            }
        },
        methods: {
            modifyBalance() {
                this.$emit('modifyBalance');
            }
        }
    }
</script>

<style>
    
</style>