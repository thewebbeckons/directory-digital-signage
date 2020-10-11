<template>
  <div class="resident">
    <div class="resident__meta">
      <div class="resident__meta-icon">Icon</div>
      <div class="resident__meta-info">
        <p class="suite">Suite {{ resident.suite }}</p>
        <p class="floor">Floor {{ resident.floor }}</p>
      </div>
    </div>
    <div class="resident__name">
      {{ fullname[0] + ',' }}<br>{{ fullname[1] }}
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'resident'
  ],
  computed: {
    fullname () {
      let fullname = this.resident.name.split(' ')
      return fullname      
    }
  },
}
</script>

<style lang="scss">
.resident {
  max-width: 200px;
  font-family: 'Source Sans Pro', Arial, Helvetica, sans-serif;
  background-color: #fff;
  box-shadow: 0 5px 10px 0 rgba(199, 199, 199, 0.25);
  border-radius: 10px;
  &__meta {
    display: flex;
    justify-content: space-between;
    background-color: #F0F0F0;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    padding: 10px 15px;
    &-icon {

    }
    &-info {
      text-align: right;
      & .suite {
        font-weight: 400;
        font-size: 15px;
        color: #1D4CC6;
      }
      & .floor {
        font-weight: 600;
        font-size: 18px;
      }
    }
  }
  &__name {
    padding: 20px 15px;
    font-weight: 300;
    font-size: 22px;
    color: rgba(0,0,0,0.5);
    font-family: 'Source Sans Pro', Arial, Helvetica, sans-serif;
  }
    
}

</style>