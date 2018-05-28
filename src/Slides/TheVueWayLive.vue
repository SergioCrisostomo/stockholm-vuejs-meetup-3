<template>
    <div class="slide-wrapper">
        <h1>The Vue API</h1>
        <h3>Who? {{name}}!</h3>
        <p>{{name}} is {{age}} years old in the year of <input-number v-model="year"></input-number></p>
        <p>{{name}} was born in <input-number v-model="born"></input-number></p>
        <p>{{name}} was born in the {{generation}}'s</p>
        <small><i>(check console logs)</i></small>
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
                console.log('computing age...');
                return this.year - this.born;
            },
            generation(){
                console.log('computing generation...');
                return String(Math.floor(this.born / 10) * 10).slice(2);
            }
        }
    }
</script>

<style scoped>
</style>
