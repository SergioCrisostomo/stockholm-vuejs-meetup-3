<template>
    <div class="slide-wrapper">
        <h1>Basic Vue component API</h1>
        <pre v-highlightjs>
            <code class="javascript">
                new Vue({
                  el: '#app',
                  mixins: [],
                  components: [],
                  props: {},
                  data() {
                    return {
                      foo: 'bar'
                    };
                  },
                  computed: {
                    someComputed() {
                      return 'something';
                    }
                  },
                  methods: {
                    someMethod() {
                      doSomething();
                    }
                  },
                  watch: {
                    someValue() {
                      doSomething();
                    }
                  },
                  mounted() {
                    console.log('Component in DOM!')
                  },
                  created() {
                    console.log('Component instanciated!');
                  }
                });
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
