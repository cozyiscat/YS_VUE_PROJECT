<template>
  <div class="">
    <br><br><br><br><br>
    <!-- //메소드로 처리하는 법 -->
    <label>성 : <input type="text" v-model="familyName1" @input="makeFullName1"></label><br>
    <label>이름 : <input type="text" v-model="name1" @input="makeFullName1"></label>
    <p>성명(method 방식) : {{ fullName1 }}</p>
    <!-- 컴퓨티드 방식으로 처리하는 법 -->
    <label>성 : <input type="text" v-model="familyName2"></label><br>
    <label>이름 : <input type="text" v-model="name2"></label>
    <p>성명(computed 방식) : {{ makeFullName2 }}</p>
    <!-- 워치 방식으로 처리하는 법 -->
    <label>성 : <input type="text" v-model="familyName3"></label><br>
    <label>이름 : <input type="text" v-model="name3"></label>
    <p>성명(watch 방식) : {{ fullName3 }}</p>
  </div>
</template>

<script>
export default {
  name: 'TestView',
  components: {
    
  },
  data() {
    return {
      fullName1:'',
      familyName1:'',
      name1:'',

      familyName2:'',
      name2:'',

      familyName3:'',
      name3:'',
      fullName3:'',

    };
  },
  watch:{
    familyName3(){
      this.fullName3 = this.familyName3 + '-' + this.name3;
    },
    Name3(){
      this.fullName3 = this.familyName3 + '-' + this.name3;
    }
  },
  computed:{
    makeFullName2(){
      return this.familyName2 + '-' + this.name2
    }
  },
  methods: {
    makeFullName1(){
      this.fullName1 = this.familyName1 + '-' + this.name1
    }
  }
};
</script>

<style scoped>

</style>