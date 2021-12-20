<template>
  <div>
    <iframe id= 'container' width="499" height="289"
    src="https://www.youtube.com/embed/bHWgc5MPnPA?autoplay=1&mute=1">
</iframe>
  </div>
</template>
<script>
export default {
  
}
</script>
<style scoped>
  #container {    
    margin: auto;
    width: 500px;
    height: 290px;
    background: white;
  }
  @media screen and (max-width: 700px) {
    #container {
      width: 80vw;
    }
  }
</style>