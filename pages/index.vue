<template>
  <div>
    <h1>Events</h1>
    <div v-if="events" class="event-list">
      <event-card
        v-for="(event, i) in events"
        :key="i"
        :event="event"
        :data-index="i"
      />
    </div>
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'

export default {
  components: { EventCard },
  asyncData(context) {
    return context.$axios
      .get('http://localhost:3003/events')
      .then((response) => {
        return {
          events: response.data,
        }
      })
      .catch((e) => {
        context.error({
          statusCode: 503,
          message: 'Unable to fetch events at this time. Please try again.',
        })
      })
  },
  head() {
    return {
      title: 'Event Listing',
    }
  },
}
</script>

<style></style>
