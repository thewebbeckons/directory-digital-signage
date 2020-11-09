<template>
  <div class="news__card">
    <div>
      <h4 class="news__date">{{ $moment().format('MMM. Do, YYYY') }}</h4>
      <h2 class="news__title">{{ post.title }}</h2>
      <p class="news__content">
        {{ post.body }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: [ 'post' ]
}
</script>

<style lang="scss">
.news {
  &__card {
    border-radius: 10px;
    background: linear-gradient(180deg, rgba(0,0,0,0) 0%,rgba(0,0,0,1) 100%), url(~assets/news_bg.jpg);
    background-position: center;
    display: flex;
    align-items: flex-end;
    padding: 160px 30px 60px 30px;
    & div {      
      letter-spacing: 1px;
    }
  }
  &__date {
    font-family: 'Source Sans Pro';
    font-weight: 400;
    font-size: 1em;
    line-height: 22px;
    color: #f8f8f8;
    margin-bottom: 5px;
  }
  &__title {
    font-family: 'Bitter';
    font-weight: 500;
    font-size: 2rem;
    line-height: 42px;
    color: #f8f8f8;
    margin-bottom: 15px;
  }
  &__content {
    font-family: 'Source Sans Pro';
    font-weight: 300;
    font-size: 1em;
    line-height: 22px;
    color: rgba(255,255,255,0.9);
  }
}

</style>