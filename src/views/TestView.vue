<template>
  <div class="">
    <!-- v-for -->
    <table>
      <thead>
        <th>제품명</th>
        <th>가격</th>
        <th>품목</th>
        <th>배송료</th>
      </thead>
      <tbody>
        <tr v-for="(item,index) in goods" v-bind:key="index">
          <td>{{item.name}}</td>
          <td>{{item.price}}</td>
          <td>{{item.cartegory}}</td>
          <td>{{item.delivery}}</td>
        </tr>
      </tbody>
    </table>

    <!-- v-if v-else -->
    <p v-if="true">호랑이</p>
    <p v-if="false">사자</p>

    <div>
      <label>국어:<input type="number" v-model="kor"></label><br>
      <label>영어:<input type="number" v-model="eng"></label><br>
      <label>수학:<input type="number" v-model="math"></label><br>
      <br>
      <p v-if="averageScore >=90">A학점</p>
      <p v-else-if="averageScore >=80">B학점</p>
      <p v-else-if="averageScore >=70">C학점</p>
      <p v-else-if="averageScore >=60">D학점</p>
      <p v-else>F학점</p>
    </div>
  </div>
  <div> 
    <button v-on:click="showScore">계산</button>
  </div>
  <div>
      <label><input type="number" v-model.number="dan">단</label>
      <button v-on:click="showDan">계산</button>
      <div v-if="calculatedDan !== null">
        <div v-for="i in 9" :key="i">
          <p>{{ calculatedDan }} * {{ i }} = {{ calculatedDan * i }}</p>
        </div>
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
      goods:[
        {"name":"마우스",price:10000, "cartegory":"PC용품","delivery":2500},
        {"name":"키보드",price:31000, "cartegory":"PC용품","delivery":2500},
        {"name":"모니터(커브드와이드)",price:2500000, "cartegory":"PC용품","delivery":0},
      ],
      // score:0,
      kor:'',
      eng:'',
      math:'',
      dan:'',
      calculatedDan: null, // 구구단 결과를 저장하는 데이터 속성
    };
  },
  methods: {
    // showMessage
    showScore(){
      alert(1+1)
    },
    showDan() {
      if (this.dan > 0) {
        // 구구단 결과를 계산하고 저장합니다.
        this.calculatedDan = this.dan;
        // 입력값을 초기화합니다.
        this.dan = '';
      } else {
        // dan 값이 0 이하인 경우 구구단 결과를 지웁니다.
        this.calculatedDan = null;
      }
    }
    },
  computed: {
    averageScore() {
      const kor = parseFloat(this.kor) || 0;
      const eng = parseFloat(this.eng) || 0;
      const math = parseFloat(this.math) || 0;
      const total = kor + eng + math;
      const count = 3; // 국어, 영어, 수학
      return count > 0 ? total / count : 0;
    }
  }
};            
</script>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
}
td,th {
  border: 1px solid #ddd;
}

</style>