<template>
  <div class="event-card" v-for="(event, index) in events" :key="index">
    <h4>{{ event.title }}</h4>
    <span>{{ event.description }}</span>
    <span>{{ event.category }}</span>
    <span>{{ event.date }}</span>
    <span>{{ event.time }}</span>
    <button @click="deleteEnvents(event.id)">Supprimer</button>
    <button>Modifier</button>
  </div>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    events: Object,
  },
  methods: {
    deleteEnvents(id) {
      this.$emit('delete-events', id)
    },
  },
}
</script>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
