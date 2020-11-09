<template>
  <div class="footer">
    <UpdateStatus />
  </div>
</template>

<script> 
export default {
  props: [ 'results' ]
}
</script>

<style lang="scss">
  .footer {
    text-align: right;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    font-size: 14px;
    & .results {
      display: flex;
      justify-content: right;
      align-items: center;
      & svg {
        margin-right: 5px;
      }
    }    
  }
</style> 