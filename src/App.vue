<template>
  <div class="container mx-auto max-w-7xl px-5 py-20">
    <p>Miguel</p>
    <div id="panzoom-element">
      <img src="https://fs-prod-cdn.nintendo-europe.com/media/images/10_share_images/games_15/virtual_console_nintendo_3ds_7/SI_3DSVC_SuperMarioBros_image1600w.jpg" alt="">
    </div>
    <button id="zoom" class="border">zoom In</button>
    <button id="zoomOut" class="ml-5 border">zoom out</button>
  </div>


</template>

<script>
import Panzoom from '@panzoom/panzoom'

export default ({
  components: {
    
  },
  mounted(){
    const elem = document.getElementById('panzoom-element')
    const button = document.getElementById('zoom')
    const button2 = document.getElementById('zoomOut')
    const panzoom = Panzoom(elem, {
      maxScale: 5,
    })
    panzoom.zoom(2, { animate: true })
    button.addEventListener('click', panzoom.zoomIn)
    button2.addEventListener('click', panzoom.zoomOut)
    elem.parentElement.addEventListener('wheel', panzoom.zoomWithWheel)
  },
  setup() {
  },
})
</script>
<style lang="scss" scoped>

</style>