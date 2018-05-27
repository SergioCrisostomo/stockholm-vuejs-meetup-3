<template>
    <div class="slide-wrapper">
        <h1>PRN Usage example 2</h1>
        <pre v-highlightjs>
            <code class="javascript">

              // generic computed property in the FormField wrapper
              title() {
                const {title} = this.fieldData.label;
                const titleString = typeof title === 'function' ? title(this) : translate(title);
                return capitalizeFirst(titleString);
              },


              // Form manifest configuration
              label: {
                icon: 'fugue-user',
                title(instance) {
                  const orgUnitType = instance.$store.getters.organization_unit_type;
                  return translate(`organization_patient_name.${orgUnitType}.indefinite`);
                },
              },

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
