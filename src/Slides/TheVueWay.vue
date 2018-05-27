<template>
    <div class="slide-wrapper">
        <h1>The Vue API</h1>
        <h3>Who? {{name}}!</h3>
        <p>{{name}} is {{age}} years old in the year of <input-number v-model="year"></input-number></p>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                name: 'John',
                born: 1978,
                year: new Date().getFullYear()
            }
        },
        computed: {
            age(){
                return this.year - this.born;
            }
        }
    }
</script>

<style scoped>
</style>
