<template>
  <div>
    <h1>Create an Event</h1>
  </div>
</template>

<script>
export default {
  head() {
    // <-- property used by vue-meta to add header tags
    return {
      title: 'Create Event ', // <-- For our title tag
      meta: [
        {
          hid: 'description',
          name: 'description', // <-- for our meta description tag
          content: 'Tou can create a new event!!!'
        }
      ]
    }
  }
}
</script>

<style scoped></style>
