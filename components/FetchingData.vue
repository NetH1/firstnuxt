<template>
  <div>
    <div v-if="$fetchState.pending">
      <div class="fixed top-0 left-0 w-full h-full">
        <div class="relative w-full h-full">
          <div class="spinner-place">
            <div class="spinner-border text-success" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <p v-else-if="$fetchState.error">
      An error occurred :(
    </p>
    <div v-else>
      <h1>Nuxt Mountains</h1>
      <ul>
        <li v-for="mountain of mountains.data" :key="mountain.id">
          <p>{{ mountain.id }}. {{ mountain.color }}</p>
        </li>
      </ul>
      <button @click="$fetch">
        Refresh
      </button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'FetchingData',
  data () {
    return {
      mountains: []
    }
  },
  async fetch () {
    this.mountains = await fetch(
      'https://reqres.in/api/products'
    ).then(res => res.json())
  },
}
</script>

<style scoped>
  .spinner-place {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>
