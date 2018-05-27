<template>
    <div class="slide-wrapper">
        <h1>PRN Calendar state tree</h1>
        <pre v-highlightjs>
            <code class="json">
                {
                  "activeUserId": 122,
                  "fadeTransitionDuration": 600,
                  "lang": "sv",
                  "langCodes": {
                    "en": "en-US",
                    "sv": "sv-SE"
                  },
                  "organization_unit_type": "SCHL",
                  "userLocked": false,
                  "weekStartDay": 1,
                  "Base": {
                    "contactinfo": "array",
                    "user": "object",
                    "userprofile": "object",
                    "users": "array",
                    "organization": "array",
                    "organizationSettings": "object"
                  },
                  "Calendar": {
                    "access": "array",
                    "calendarEvents": "array",
                    "countryDates": "array",
                    "currentCalendarUser": "object",
                    "displayCalendarFromUser": "array",
                    "eventcategory": "array",
                    "eventprintouttemplate": "array",
                    "hideFilters": "object",
                    "layers": "array",
                    "settings": "object"
                  },
                  "Patients": {
                    "healthcareunit": "array",
                    "patient": "array"
                  },
                  "Tasks": {
                    "task": "array"
                  },
                  "Requests": {
                    "activeRequestsToEndpoint": "object",
                    "lastUpdatedComponent": "string",
                    "registeredComponents": "object"
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
