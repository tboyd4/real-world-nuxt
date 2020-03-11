<template>
  <div>
    <h1>{{ event.title }}</h1>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: this.event.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'What you should know about event ' + this.event.title
        }
      ]
    }
  },
  async asyncData({ $axios, error, params }) {
    try {
      const { data } = await $axios.get('http://localhost:3001/events/' + params.id)
      return {
        event: data
      }
    } catch (e) {
      error({ statusCode: 503, message: 'Cannot fetch event# ' + params.id + ' at this time.' })
    }
  }
}
</script>

<style lang="scss" scoped></style>
