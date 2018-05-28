<template>
    <div class="slide-wrapper">
        <h1>Basic vue component</h1>
        <p><i>(source: <a href="https://jsfiddle.net/65k8qsgd/6/" target="_blank">jsfiddle.net/65k8qsgd/6/</a>)</i></p>
        <pre v-highlightjs>
            <code class="javascript">
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
                        },
                        generation(){
                            return String(Math.floor(this.born / 10) * 10).slice(2);
                        }
                    }
                }
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
