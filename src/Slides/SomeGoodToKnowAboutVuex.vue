<template>
    <div class="slide-wrapper">
        <h1>Good to know about Vuex</h1>
        <pre v-highlightjs>
            <code class="javascript">
                strict: process.env.NODE_ENV !== 'production'
            </code>
            <code class="javascript">
                modules: Modules,
                namespaced: true,
            </code>
            <code class="javascript">
                getters: {
                  doneTodosCount: (state, getters) => {
                    return getters.doneTodos.length
            </code>
            <code class="javascript">
                mutations: {
                  increment (state, payload) {
                    state.count += payload.amount
            </code>
            <code class="javascript">
                store.dispatch('actionA').then(() => {
                    // ...
                actions: {
                  actionA ({commit, dispatch, getters, state}) {
                    return new Promise((resolve, reject) => {
            </code>
        </pre>
    </div>
</template>

<script>
    export default {
        name: "Start"
    }
</script>


<style scoped>

</style>
