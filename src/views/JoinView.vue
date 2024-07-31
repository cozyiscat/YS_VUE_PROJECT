<template>
  <div class="join">
    <h2>{{title}}</h2>
    <div>
        <h4>사용자 이름</h4>
        <input class="box" type="text" v-model="textbox">
    </div>
    <div>
        <h4>이메일</h4>
        <input class="box" type="email" v-model="emailbox">
    </div>
    <div>
        <h4>비밀번호</h4>
        <input class="box" type="password" v-model="passwordbox">
    </div>
    <div>
        <h4>비밀번호 확인</h4>
        <input class="box" type="password" v-model="passwordbox">
    </div>
    <div>
        <h4>성별</h4>
        <label><input type="radio" value="남성" v-model="genderbox">남성</label>
        <label><input type="radio" value="여성" v-model="genderbox">여성</label>
        <p>당신의 성별은 {{genderbox}} 입니다.</p>
    </div>
    <div>
        <h4>좋아하는 음식</h4>
        <select  class="box" name="" id="" v-model="favbox">
            <option value="한식">한식</option>
            <option value="중식">중식</option>
            <option value="일식">일식</option>
            <option value="양식">양식</option>
            <option value="고양이사료">고양이사료</option>
        </select>
        <p>당신이 좋아하는 음식은 {{favbox}} 입니다.</p>

    </div>
    <div>
        <label><input type="checkbox" v-model="openbox" true-value="동의" false-value="비동의">정보공개 {{openbox}}</label>
    </div>
    <div>
        <button>가입하기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'JoinView',
  components: {
    
  },
  data() {
    return {
      title:'회원가입',
      textbox:'코지',
      emailbox:'yuiop@abc.com',
      passwordbox:1234,
      genderbox:'여성',
      openbox: '비동의',
      favbox: '고양이사료',
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
.join {
    width: 400px;
    padding: 30px 20px;
    margin: 30px auto;
    text-align: left;
    /* border: 1px solid black; */
    background-color: white;
    border-radius: 5px;
      box-shadow: 0 13px 27px -5px rgba(50,50,93,0.25),
              0  8px 16px -8px rgba(0,0,0,0.3),
              0 -6px 16px -6px rgba(0,0,0,0.25);
}
.box {
    width: 380px;
    height: 40px;
    padding: 0 10px;
    text-align: left;
    border: 1px solid #bbb;
    border-radius: 5px;
    }
div {margin-top: 20px;}
div:nth-child(9) {text-align: center}
button {
    width: 100px;
    height: 40px;
    font-size: 15px;
    color: white;
    border: none;
    border-radius: 5px;
    background-color: royalblue;
    cursor: pointer;
    }
</style>