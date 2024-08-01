<template>
  <div class="">
    <input type="checkbox" id="cbtn_agree">
    <label for="cbtn_agree">동의</label> <br>
    <label><input type="checkbox" v-model="agree">동의</label><br>
    <label><input type="checkbox" v-model="agree2" true-value="동의" false-value="비동의">{{agree2}}</label><br>

    <div>
      <p>기본 피자에 원하시는 토핑을 추가하세요</p>
      <label><input type="checkbox" v-model="pizza" value="치즈">치즈</label><br>
      <label><input type="checkbox" v-model="pizza" value="파인애플">파인애플</label><br>
      <label><input type="checkbox" v-model="pizza" value="페퍼로니">페퍼로니</label><br>
      <p>당신이 선택하신 토핑은 {{ pizza }}입니다.</p>
    </div>
    <div>
      <p>당신의 탕수육 취향은?</p>
      <label><input type="radio" v-model="sweet" value="부먹">부먹</label><br>
      <label><input type="radio" v-model="sweet" value="찍먹">찍먹</label><br>
      <p>당신이 선택하신 토핑은 {{ sweet }}입니다.</p>

    </div>
  </div>
</template>

<script>
export default {
  name: 'TestView',
  components: {
    
  },
  data() {
    return {
      agree:true,
      agree2:"비동의",
      pizza:[],
      sweet:'',
    };
  },

  methods: {
    
  }
};
</script>

<style scoped>

</style>