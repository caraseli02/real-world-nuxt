<template>
  <div>
    <h1>Event #{{ event.title }}</h1>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: '_id',
  async asyncData({ store, error, params }) {
    try {
      await store.dispatch('events/fetchEvent', params.id)
    } catch (e) {
      error({
        statusCode: 503,
        message: 'Unable to fetch event #.' + params.id
      })
    }
  },
  head() {
    // <-- property used by vue-meta to add header tags
    return {
      title: 'Event #' + this.event.title, // <-- For our title tag
      meta: [
        {
          hid: 'description',
          name: 'description', // <-- for our meta description tag
          content: 'What you need  to know abaut event #' + this.event.title
        }
      ]
    }
  },
  computed: mapState({
    event: (state) => state.events.event
  })
}
</script>

<style scoped></style>
