<template>
  <div>
    <h1>Event #{{ this.$route.params.id }}</h1>
  </div>
</template>

<script>
export default {
  computed: {
    id() {
      return this.$route.params.id
    },
  },
  head() {
    return {
      title: `Event #${this.id}`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: `Details for event ${this.id}`,
        },
      ],
    }
  },
}
</script>

<style></style>
