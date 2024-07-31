<template>
  <div class="basic">
    <h1>Hello, {{title}}!</h1>
    <h1>{{title}}는 수원 장안구에 있습니다.</h1>
    <h1>{{message}}</h1>
    <p v-html="message"></p>
  </div>
  <div>
    <input type="text" v-model="nickname"/>
  </div>
  <div>
    <input type="number" v-model="age"/>
  </div>
  <div>
    <textarea v-model="message" cols="30" rows="10"></textarea>
  </div>
  <div>
    <select name="city" v-model="city">
        <option value="01">서울</option>
        <option value="02">부산</option>
        <option value="03">대구</option>
        <option value="04">수원</option>
    </select>
  </div>
  <div>
    <label><input type="checkbox" v-model="cbox">{{cbox}}</label>
    <label><input type="checkbox" v-model="cbox2" true-value="동의" false-value="비동의">{{cbox2}}</label>
  </div>
  <div>
    <p>좋아하는 음식은?</p>
    <label><input type="checkbox" v-model="goodfood" value="마라탕">마라탕</label>
    <label><input type="checkbox" v-model="goodfood" value="민트초코">민트초코</label>
    <label><input type="checkbox" v-model="goodfood" value="홍어삼합">홍어삼합</label>

    <p>당신이 좋아하는 음식은 {{goodfood}} 입니다.</p><br>
    <p>싫어하는 음식은?</p>
    <label><input type="checkbox" v-model="badfood" value="마라탕">마라탕</label>
    <label><input type="checkbox" v-model="badfood" value="깻잎">깻잎</label>
    <label><input type="checkbox" v-model="badfood" value="홍어삼합">홍어삼합</label>
    <p>당신이 싫어하는 음식은 {{badfood}} 입니다.</p>
  </div>
  <div>
    <p>당신의 성별은?</p>
    <label><input type="radio" v-model="gender" value="남">남</label>
    <label><input type="radio" v-model="gender" value="녀">녀</label>
    <p>당신은 {{gender}}</p>
  </div>
    <h3>------속성연결----------</h3>
    <div>
    <img v-bind:src="imgsrc" alt="" v-bind:title="tooltip"/>
  </div>
  <div>
    <button v-bind:disabled="show1">눌러주세요</button>
    <button v-bind:disabled="show2">눌러주세요</button>
  </div>
  <div>
    <button v-bind:style="btn1">눌러주세요</button>
    <button v-bind:style="btn2">눌러주세요</button>
  </div>
  <br><br><br><br><br><br>
</template>

<script>
export default {
  name: 'BasicView',
  components: {
    
  },
  data() {
    return {
      title:'연세 IT',
      message:'<b>연세IT<b>는 <b><span style="color:red;">5년</span></b> 우수 직업학교입니다.',
      nickname: '돌쇠',
      age: 22+3,
      city: "04",
      cbox: false,
      cbox2: "비동의",
      goodfood:[],
      badfood:[],
      gender:'남',
      imgsrc:"https://borgssam.github.io/MySite/img/album_01.jpg",
      tooltip:'툴팁메세지',
      show1:true,
      show2:false,
      btn1:{backgroundColor:'blue',
        color:'yellow',
        fontSize:'32px',
      },
      btn2:{backgroundColor:'red',
        color:'white',
        fontSize:'32px',
      },
    };
  },
  setup() {
    
  },
  created() {
    
  },
  mounted() {
    
  },
  unmounted() {
    
  },
  methods: {
    
  }
};
</script>

<style scoped>

</style>