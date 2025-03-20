<script>
import NewFrom from '@/components/NewFrom.vue'
import EventSercice from '../services/EventService.js'

export default {
  components: {
    NewFrom,
  },
  methods: {
    newEvents(newEvent) {
      EventSercice.addEvent(newEvent).catch((err) => console.log(err))
    },
  },
}
</script>

<template>
  <NewFrom @new-event="newEvents"></NewFrom>
</template>

<style scoped></style>
