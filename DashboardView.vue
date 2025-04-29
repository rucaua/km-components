<script>
export default {
  name: "DashboardView",
  props: {
    items: {
      type: Array,
      default: () => []
    },
  }
}
</script>

<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
    <div v-for="(item, index) in items" :key="index"
         class="w-full bg-white shadow-md rounded-lg p-4 border-t-4"
         :class="`border-${item.colorType}`">
      <h2 class="text-xl font-bold text-gray-700">{{ item.title }}</h2>
      <p class="text-2xl font-semibold" :class="`text-${item.colorType}`">{{ item.value }}</p>
    </div>
  </div>
</template>
