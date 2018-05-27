<template>
    <div class="slide-wrapper">
        <h1>Native setters - basic computed functionality</h1>
        <p><i>(source: <a href="https://jsfiddle.net/65k8qsgd/6/" target="_blank">jsfiddle.net/65k8qsgd/6/</a>)</i></p>
        <pre v-highlightjs>
            <code class="javascript">
                function newPerson(name, born, year) {
                  const internalState = {name, born, year};
                  const dependencies = {};
                  let watcher = null;

                  const registerDependency = (key) => {
                    if (!dependencies[key]) dependencies[key] = [];
                    dependencies[key].push(watcher);
                  };

                  const state = {
                    computedAge: function(fn) {
                      const getter = (state) => fn(state.year - state.born);
                      watcher = getter;
                      getter(state);
                      watcher = null;
                    }
                  };

                  Object.keys(internalState).forEach(key => {
                    Object.defineProperty(state, key, {
                      get() {
                        if (watcher) registerDependency(key);
                        return internalState[key];
                      },
                      set(newValue) {
                        internalState[key] = newValue;
                        dependencies[key].forEach(fn => fn(internalState));
                      },
                      enumerable: true
                    });
                  });

                  return state;
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
