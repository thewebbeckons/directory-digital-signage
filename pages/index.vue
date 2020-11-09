<template>
  <div class="main-content">    
    <div class="residents">
      <h1 class="subtitle">Residents</h1>
      <div class="residents-grid">
        <ResidentCard v-for="resident in residents" :key="resident.id" :resident="resident" />
      </div>
      <div class="scroll">
        <fa :icon="['fas', 'chevron-down']" class="fa-2x" />
      </div>      
    </div>
    <div class="news-section">
      <h1 class="subtitle">Today's News</h1>
      <NewsCard :post="post" />
    </div>
  </div>
</template>

<script>
export default {  
  data () {
    return {
      residents: [],
      post: []
    }
  },
  activated() {
    if (this.$fetchState.timestamp <= Date.now() - 60000) {
      this.$fetch()
    }
  },
  async fetch() {
    this.residents = await fetch('https://jsonplaceholder.typicode.com/users').then(res => res.json())
    this.post = await fetch('https://jsonplaceholder.typicode.com/posts/1').then(res => res.json())
  },
  methods: {
    sendUpdate(time) {
      this.$emit('update-time', time)
    } 
  }
}
</script>

<style lang="scss">
.main-content {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  height: 100%;
}
.residents {
  &-grid {
    display:flex;
    flex-wrap: wrap;
    margin-right: 50px;
    overflow-y: scroll;
    max-height: calc(70vh - 100px);
    margin-bottom: 25px;   
    &::-webkit-scrollbar {
      display:none;
    }
  }
}
.scroll {
  display: flex;
  justify-content: center;
  margin-bottom: 25px;
}
.subtitle {
  font-family: 'Bitter', Arial, Helvetica, sans-serif;
  font-weight: 300;
  font-size: 38px;
  width: 100%;
  padding-bottom: 25px;
}
hr {  
  width: 450px;
  height: 4px;
  border: none;
  background-color: #000;
}
@media screen and (max-width: 1080px) and (orientation: portrait) {
  .main-content {
    display: block;
  }
  .residents-grid {
    margin-right: 0;
    margin-bottom: 25px;
    max-height: calc(50vh - 71px);
  }
}
</style>
