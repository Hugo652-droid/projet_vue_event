<script>
export default {
  data() {
    return {
      category: '',
      title: '',
      description: '',
      location: '',
      date: '',
      time: '',
    }
  },
  methods: {
    submitForm() {
      let newEvent = {
        category: this.category,
        title: this.title,
        description: this.description,
        location: this.location,
        date: this.date,
        time: this.time,
      }
      this.$emit('new-event', newEvent)
    },
  },
}
</script>

<template>
  <form @submit.prevent="submitForm">
    <h1>Titre</h1>
    <input v-model="title" />
    <h1>Catégorie</h1>
    <select v-model="category">
      <option value="Loisirs">Loisirs</option>
    </select>
    <h1>Description</h1>
    <textarea v-model="description" />
    <h1>Lieux</h1>
    <input v-model="location" />
    <h1>Date</h1>
    <input type="date" v-model="date" />
    <h1>Heure</h1>
    <input type="time" v-model="time" />
    <input type="submit" value="Ajouter" />
  </form>
</template>

<style scoped></style>
