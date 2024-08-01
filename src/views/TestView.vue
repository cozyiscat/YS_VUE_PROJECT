<template>
  <div class="">
    <input type="text" value="333"/><br>
    <input type="text" v-bind:value="nick"/><br>
    <input type="text" v-model="nick"/><br>
    <input type="number" v-model="age"><br>
    <input type="number" v-model.number="age"><br>
    <textarea cols="30" rows="10">동해물과 백두산이</textarea><br>
    <textarea cols="30" rows="10" v-model="messeage"></textarea><br>
    <select name="" id="">
      <option value="01">서울</option>
      <option value="02">부산</option>
      <option value="03">대구</option>
      <option value="04">수원</option>
    </select>
    <select v-model="city">
      <option value="01">서울</option>
      <option value="02">부산</option>
      <option value="03">대구</option>
      <option value="04">수원</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'TestView',
  data() {
    return {
      nick:"노래하는 작은바위",
      age:30,
      messeage:"깊은산속 <i>옹달샘</i> 누가와서 먹나요",
      city:'03',
    };
  },
  methods: {
    
  }
};
</script>

<style scoped>

</style>