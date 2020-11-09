<template>
  <div class="resident">
    <div class="resident__icon"><fa :icon="['far', 'id-card']" class="fa-2x" /></div>
    <div class="resident__name">
      {{ resident.name }}
    </div>
    <div class="resident__meta">      
      <span class="floor"><fa :icon="['far', 'building']" />Floor {{ 2 }}</span>
      <span class="suite"><fa :icon="['fas', 'house-user']" />Suite {{ 201 }}</span>
    </div>   
  </div>
</template>

<script>
export default {
  props: [
    'resident'
  ],
}
</script>

<style lang="scss">
.resident {
  width: 100%;
  font-family: 'Source Sans Pro', Arial, Helvetica, sans-serif;
  background-color: #fff;
  box-shadow: 0 5px 10px 0 rgba(199, 199, 199, 0.1);
  border-radius: 10px;
  padding: 15px 20px;
  display: flex;
  align-items: center;
  margin-bottom: 40px;
  // Icon Styles  
  &__icon {
    width: 5%;
  }
  // Name
  &__name {
    width: 60%;   
    font-weight: 300;
    font-size: 22px;
    color: rgba(0,0,0,0.5);
    font-family: 'Source Sans Pro', Arial, Helvetica, sans-serif;
  }   
  // Meta Information
  &__meta {
    text-align: right;
    display: flex;    
    justify-content: flex-end;
    width: 35%;
    & > * {
      margin-left: 15px;
    }
    & .suite {
      font-weight: 400;
      font-size: 1rem;
      color: #1D4CC6;
      & svg {
        margin-right: 5px;
      }
    }
    & .floor {
      font-weight: 700;
      font-size: 1rem;
      & svg {
        margin-right: 5px;
      }
    }
  }
   
}

</style>