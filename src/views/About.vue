<template>
  <main>
    <div class="overlay"></div>
    <div class="header">
      <h1 class="title animate-this">
        About page
      </h1>
    </div>
  </main>
</template>


<script>
import gsap, {Power1} from 'gsap';
export default {
  name: 'About',
  mounted () {
    gsap.from(".overlay",0.8, {
      x: 0,
      y:0,
      transformOrigin: "0% 50%",
      ease : Power1.easeInOut
    })
    gsap.to('h1',1,{
      y:20,
      delay:.2,
      opacity:1
      
    })
  }
}
</script>


<style>
h1 {
  position: absolute;
  top: 38%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-family: "Cosi Azure";
  font-size: 84px;
  opacity: 0;
}
.overlay{
  position: absolute;
  left: 0;
  top: 0;
  background-color: lightgreen;
  width: 100%;
  height: 100%;
  transform: translateX(100%);
}
</style>

