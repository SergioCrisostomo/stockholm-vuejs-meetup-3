<template>
    <div class="slide-wrapper">
        <h1>PRN Usage example 1</h1>
        <pre v-highlightjs>
            <code class="javascript">
              import {mapGetters} from 'vuex';
              const vuexGetters = {
                ...mapGetters('Calendar', ['calendarsUserCanWrite', 'eventcategory', 'settings']),
              };
              // .....
              [{
                config: {
                  fieldType: 'select-one',
                  name: 'owner',
                  options: vuexGetters.calendarsUserCanWrite,
                },
                label: {
                  alt: '',
                  icon: 'fugue-calendar-share',
                  title: 'calendar_owner',
                },
              }, ... ]
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
