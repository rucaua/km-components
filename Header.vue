<template>
  <header class="bg-main text-white p-4 flex items-center justify-between">
    <!-- Sidebar Toggle Button -->
    <button
      class="text-white cursor-pointer hover:text-gray-300 transition-all"
      title="Toggle Sidebar"
      @click="$emit('toggle-sidebar')"
    >
      <font-awesome :icon="['fas', 'bars']"/>
    </button>

    <h1 class="text-xl font-bold capitalize">
      {{ title }}
    </h1>

    <!-- Optional Header Button -->
    <div v-if="showOptionalButton">
      <button
        class="bg-secondary text-white py-2 px-4 rounded hover:bg-opacity-80"
        @click="handleOptionalButtonClick"
      >
        Action
      </button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    showOptionalButton: {
      type: Boolean,
      default: false,
    }
  },
  computed: {
    title() {
      return this.$route.name;
    }
  },
  methods: {
    handleOptionalButtonClick() {
      this.$emit("optional-button-click");
    },
  },
};
</script>
