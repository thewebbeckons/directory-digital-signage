<template>
  <div id="content">
    <Header />
    <Nuxt keep-alive />
    <Footer />
  </div>
</template>
<script>
export default {
  methods: {

  }
}
</script>
<style lang="scss">
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box; 
  background: linear-gradient(180deg, rgba(255,255,255,0) 0%, rgba(255,255,255,0.7) 40%, rgba(255,255,255,0.99) 70%, rgba(255,255,255,1) 100%), url(~assets/background.jpg);
  background-position: center;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
/* width */
::-webkit-scrollbar {
  margin-left: 5px;
  width: 5px;
}
/* Track */
::-webkit-scrollbar-track {
  background: #fcfcfc;
}
/* Handle */
::-webkit-scrollbar-thumb {
  background: rgb(216, 216, 216);
}
/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}

#content {
  margin: 0 60px;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 25vh 70vh 1fr;
  height: 100vh;
}
@media screen and (max-width: 1080px) and (orientation: portrait) {
  #content {
    margin: 0 60px;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 15vh 80vh 1fr;
    height: 100vh;
  }  
}
</style>
