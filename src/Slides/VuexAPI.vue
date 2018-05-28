<template>
    <div class="slide-wrapper">
        <h1>Basic Vuex concepts</h1>
        <pre v-highlightjs>
            <code class="javascript">
                const actions = {
                    // async logic goes here and triggers a mutation
                };

                const mutations = {
                    // here we actually do `state = newState`
                };

                const getters = {
                    // "computed" property for state, for +/- complex logic
                };

                export default {
                  actions,
                  getters,
                  mutations,
                  state: {
                    // the source of truth
                  },
                };
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
