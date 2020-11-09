<template>
  <div class="status">
    <svg height="20" width="20">
      <circle v-if="$nuxt.isOffline" cx="10" cy="10" r="7" fill="red" />
      <circle v-else cx="10" cy="10" r="7" fill="#00CD08" />
    </svg>
  </div>
</template>

<script> 
export default {
  data () {
    return { 
      status: null
    }
  },
  mounted() {
    window.addEventListener('offline', this.updateStatus('offline'))
    window.addEventListener('online', this.updateStatus('online'))
  },
  methods: {
    updateStatus(type) {
      this.status = type
    }
  }
}
</script>

<style lang="scss">  
.status {
  display: flex;
  & svg {
    margin-right: 5px;
  }
}
</style> 