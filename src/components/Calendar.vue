<template>
  <vue-cal
    class="calendar"
    hide-view-selector
    default-view="week"
    :disable-views="['years', 'year', 'month', 'day']"
    :events="events"
    hide-weekends
  >
    <template v-slot:no-event>-</template>
  </vue-cal>
</template>

<script>
import VueCal from "vue-cal";
import "vue-cal/dist/vuecal.css";
import { mapState } from "vuex";

export default {
  name: "Calendar",
  components: {
    VueCal
  },

  computed: mapState({
    events: "calendarCourses"
  })
};
</script>

<style scoped>
div {
  height: 80vh;
}

.calendar {
  font-size: 0.8em;
}

@media screen and (max-width: 450px) {
  div {
    height: 60%;
    width: 80%;
  }
}
</style>