<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>{{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>
import { computed, ref, watch } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const search = ref('')
    const names = ref(['aabounak','abiari','mashad','mgrissen','oel-ouar','oel-yous', 'ztaouil'])

    watch(search, () => {
      
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.startsWith(search.value))
    })
    return { names, search, matchingNames }
  }
}
</script>
