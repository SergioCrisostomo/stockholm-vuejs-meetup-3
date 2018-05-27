<template>
    <div class="slide-wrapper">
        <h1>Native setters - the basics</h1>
        <p><i>(source: <a href="https://jsfiddle.net/65k8qsgd/2/" target="_blank">jsfiddle.net/65k8qsgd/2/</a>)</i></p>
        <pre v-highlightjs>
            <code class="javascript">
                function newPerson(name, born, year) {
                  const state = {
                    name: name,
                    born: born,
                    year: year
                  };

                // I can do things when I get this value
                Object.defineProperty(state, 'age', {
                    get() {
                      return state.year - state.born;
                    },
                    enumerable: true
                  });
                  return state;
                }

                const Anna = newPerson('Anna', 1978, 2018);
                console.log(Anna.born, Anna.age); // 1978, 40

                Anna.born = 2010;
                console.log(Anna.age); // 8
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
