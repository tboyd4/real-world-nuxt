<template>
  <div>
    <h1>Events</h1>
    <event-card
      v-for="(event, index) in events"
      :key="index"
      :event="event"
      :data-index="index"
    ></event-card>
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
export default {
  head() {
    return {
      title: 'Event Listing'
    }
  },
  components: {
    EventCard
  },
  async asyncData({ $axios, error }) {
    try {
      const { data } = await $axios.get('http://localhost:3001/events')
      return {
        events: data
      }
    } catch (e) {
      error({ statusCode: 503, message: 'Cannot fetch events at this time.' })
    }
  }
}
</script>

<style scoped></style>
