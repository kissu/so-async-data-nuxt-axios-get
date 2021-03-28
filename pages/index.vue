<template>
  <div>
    <p>fetched data below</p>
    <p>{{ fetchedData }}</p>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const response = await $axios.$get(
      'https://jsonplaceholder.typicode.com/todos/1',
      {
        headers: {
          'X-AUTH-TOKEN': '### TOKEN HARDCODED ###',
          'Content-Type': 'application/json',
        },
      }
    )
    return { fetchedData: response }
  },
}
</script>
