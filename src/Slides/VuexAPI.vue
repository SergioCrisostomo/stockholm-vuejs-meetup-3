<template>
    <div class="slide-wrapper">
        <h1>Vuex consuming patterns</h1>
        <pre v-highlightjs>
            <code class="javascript">
                computed: {
                  totalPrice () {
                    return this.ammount * this.$store.getters.products[this.productId];
                  }
                }
            </code>
            <code class="javascript">
              computed: {
                ...mapGetters(['products', 'clientDiscountRate'])
              }
            </code>
            <code class="javascript">
              computed: {
                ...mapState(['products', 'clientDiscountRate'])
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
