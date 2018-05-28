<template>
    <div class="slide-wrapper">
        <h1>Vuex docs example with async commiting</h1>
        <pre v-highlightjs>
            <code class="javascript">

                actions: {
                  checkout ({ commit, state }, products) {
                    // save the items currently in the cart
                    const savedCartItems = [...state.cart.added]
                    // send out checkout request, and optimistically
                    // clear the cart
                    commit(types.CHECKOUT_REQUEST)
                    // the shop API accepts a success callback and a failure callback
                    shop.buyProducts(
                      products,
                      // handle success
                      () => commit(types.CHECKOUT_SUCCESS),
                      // handle failure
                      () => commit(types.CHECKOUT_FAILURE, savedCartItems)
                    )
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
