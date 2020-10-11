<template>
  <p class="updated">
    <svg height="20" width="20">
      <circle cx="10" cy="10" r="7" fill="#00CD08" />
    </svg>
    Updated Oct. 7th 6:15 pm
  </p>
</template>

<script> 
export default {

}
</script>

<style lang="scss">
  .updated {
    text-align: right;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    margin: 1rem;
    font-size: 14px;
    & svg {
      margin-right: 5px;
    }
  }
</style> 