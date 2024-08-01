<template>
  <div class="">
    <!-- 속성연결 -->
    <img src='https://borgssam.github.io/MySite/img/album_01.jpg' title="가방 든 사나이" alt="">
    <img v-bind:src="imgSrc" alt="" v-bind:title="imgTitle">
  </div>
  <div>
    <button :disabled="btn_01" :style="color_red">버튼</button>
    <button :disabled="btn_02" :style="color_blue">버튼</button>
  </div>
</template>

<script>
export default {
  name: 'TestView',
  components: {
    
  },
  data() {
    return {
      imgSrc:'https://borgssam.github.io/MySite/img/album_01.jpg',
      imgTitle:'가방 든 사나이',
      btn_01:true,
      btn_02:false,
      color_red:{color:"red", fontSize:'24px'},
      color_blue:{color:'blue', fontSize:'24px'},
    };
  },

  methods: {
    
  }
};
</script>

<style scoped>

</style>