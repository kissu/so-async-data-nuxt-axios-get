<template>
  <div>
    <p>fetched data below</p>
    <p>{{ fetchedData }}</p>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, $config: { secureToken } }) {
    const response = await $axios.$get(
      'https://jsonplaceholder.typicode.com/todos/1',
      {
        headers: {
          'X-AUTH-TOKEN': secureToken,
          'Content-Type': 'application/json',
        },
      }
    )
    return { fetchedData: response }
  },
}
</script>
