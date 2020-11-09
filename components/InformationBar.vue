<template>
  <div class="info-section">
    <div class="info-section__date">
      <fa :icon="['far', 'calendar-alt']" /> {{ $moment().format('MMMM Do YYYY') }}
    </div>
    <div class="info-section__time">
      <fa :icon="['far', 'clock']" /> {{ $moment(timeNow).format('h:mm A') }}
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      time: Date.now(),
      timer: null
    }
  },
  computed: {
    timeNow () {
      return this.time
    }
  },
  mounted() {
    // update time every second
    window.setInterval(this.updateTime, 1000)
  },
  methods: {
    updateTime() {
      const now = Date.now()
      this.time = now
    }
  }
}
</script>

<style lang="scss">
.info-section {
  display: flex;
  justify-content: space-between;  
  align-items: center;
  padding: 60px 0;
  font-size: 26px;
  font-family: 'Source Sans Pro', Arial, Helvetica, sans-serif;
  line-height: 1;
  &__date {
    display:flex;
    align-items: center;
    & .svg-inline--fa {
      margin-right: 5px;
    }
  }
  &__time {
    display: flex;
    align-items: center;
    transition: all 1s;
    & .svg-inline--fa {
      margin-right: 5px;
    }
  }
}
</style>