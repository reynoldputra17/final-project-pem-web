<template>
  <div
    class="z-50 w-fit bottom-12 right-12 fixed alert shadow-lg flex transform transition-all duration-500 cursor-pointer"
    :class="this.status ? 'alert-success' : 'alert-error'"
    @click="this.$emit('close')"
  >
    <div v-if="this.status == true">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="stroke-current flex-shrink-0 h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
      >
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          strokeWidth="2"
          d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
        />
      </svg>
      <span>{{ msg }}</span>
    </div>
    <div v-else>
      <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current flex-shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
      <span>{{ msg }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["msg", "status"],
  methods: {
    async close() {
      this.$parent.close;
    },
  },
};
</script>
