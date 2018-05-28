<template>
    <div class="slide-wrapper">
        <h1>Using Vuex state</h1>
        <h2>How to?</h2>
        <ul>
            <li>Share state between components: just use mappedGetters or `this.$store.youProperty`</li>
            <li>Complex data structure: np! and if needed use modules</li>
            <li>Update the data in one single place with clear update patterns: That is the foundation of the Store concept</li>
            <li>Make an app reactive to data change: use getters and it gets built-in!</li>
            <li>How to do it consistent? Use unidirectional Data Flow and it gets built-in to your app</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Start"
    }
</script>


<style scoped>

</style>
