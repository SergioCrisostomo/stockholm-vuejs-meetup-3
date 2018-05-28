<template>
    <div class="slide-wrapper">
        <h1>Using component state</h1>
        <h2>How to?</h2>
        <ul>
            <li>Share state between components: - event bus/props</li>
            <li>Complex data structure: component (complexity) doesn't scale</li>
            <li>Update the data in one single place with clear update patterns: which component owns which data "original"?</li>
            <li>Make an app reactive to data change: ok if internal state, or receiving change via props. Complex if cross components</li>
            <li>How to do it consistent?: try and error, a lot of bugs... prepare to abandon early ideas and refactor</li>
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
