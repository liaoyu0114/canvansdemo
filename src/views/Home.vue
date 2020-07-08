<template>
  <div class="home">
    <div>
      <hexagon v-for="item in 5 " :key="item"></hexagon>
    </div>
    <div style="transform: translate(0px, -56.75px)">
      <hexagon  v-for="item in 6" :key="item" :src="src"></hexagon>
    </div>
    <div  style="transform: translate(0, -113.5px)">
      <hexagon v-for="item in 5" :key="item"></hexagon>
    </div>
    <div style="transform: translate(0px, -170.25px)">
      <hexagon  v-for="item in 6" :key="item"></hexagon>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Hexagon from '@/components/Hexagon.vue'

export default {
  name: 'Home',
  components: {
    Hexagon
  },
  data() {
    return {
      src: "https://dss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1354268575,1268995723&fm=26&gp=0.jpg"
    }
  }
}
</script>

<style scoped>
  .home {
    background: #ffc0cb;
    width: 100vw;
    height: 100vh;
    display: inline-block;

    /*transform: translateX(100px);*/
  }
.home div {
  display: inline-block;
}
  .bar-rotate-left {
    width: 200px;
    height: 231px;
    overflow: hidden;
    transform: rotate(60deg);
    display: inline-block;
  }

  .bar-rotate-right {
    width: 200px;
    height: 231px;
    overflow: hidden;
    transform: rotate(60deg);
    display: inline-block;
  }

 .bar-horizontal {
    width: 200px;
    height: 232px;
    background: #FFFFFF;
    transform: rotate(-120deg);
    display: flex;
    justify-content: center;
    align-items: center;
  }

.bar-horizontal:hover {
    background: #F0F0F0;
  }
</style>
