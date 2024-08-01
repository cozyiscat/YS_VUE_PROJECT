<template>
  <div class="">
    <select name="" id="" v-model="city" @change="changeCity">
      <option value="서울">서울</option>
      <option value="부산">부산</option>
      <option value="대전">대전</option>
      <option value="수원">수원</option>
      <option value="광주">광주</option>
    </select>
    <p>{{ message }}</p>
  </div>
  <div>
    <p><label>이메일<input type="text" @input="changeEmail" placeholder="이메일을 입력하세요"
      v-model="emailValue"></label>
      <span>{{ msgEmail }}</span></p>

      <!-- 8자 이상 숫자,문자 조합 @#제외 비번과 비번확인 일치 -->
      <p><label >비밀번호<input type="text" v-model="pwd1"
    @input="changePwd" placeholder="비밀번호를 입력하세요"></label>
    <span>{{msgPwd1}}</span></p>
    <p><label >비밀번호확인<input type="text"
    @input="changePwd2" placeholder="비밀번호확인을 입력하세요"></label>
    <span>{{msgPwd2}}</span></p>

  </div>
</template>

<script>

export default {
  name: 'TestView',
  components: {
    
  },
  data() {
    return {
      city:'광주',
      message:'안녕하세요 반갑습니다',
      emailValue:'',
      msgEmail:'이메일을 입력하세요',
      pwd1:'',
      pwd2:'',
      msgPwd1:'비밀번호를 입력하세요',
      msgPwd2:'비밀번호 확인을 입력하세요',
    };
  },
  methods: {
    changeEmail(){
      // this.emailValue이 형식에 맞는지 체크
      const emailExp =  /^[^\s@]+@[^\s@]+\.[^\s@]+$/; //문자열 + @ + 문자열 + . + 문자열
      if(this.emailValue.length == 0){
        this.msgEmail = '이메일을 입력하세요';
      } else if(emailExp.test(this.emailValue) == true){
        this.msgEmail = '정상적인 이메일 주소입니다.';
      }else{
        this.msgEmail = '이메일 주소가 올바르지 않습니다.';
      }
    },
    checkPwd(pwd){
      let msg = '';
      // 문자열 길이
      const len = pwd.length;
      // 문자 포함여부 
      const hasWord = /[a-zA-z]/.test(pwd);
      // 숫자 포함여부 
      const hasNum = /[\d]/.test(pwd);
      //금지어 포함여부
      const hasForbid = /[@#]/.test(pwd);
      // 비번확인 일치여부
      if(len<8){
        msg = '비밀번호는 8자리 이상이어야 합니다.';
      }else if(!hasWord){
        msg = '비밀번호에는 문자가 포함되어야 합니다.';
      } else if(!hasNum){
        msg = '비밀번호에는 숫자가 포함되어야 합니다.';
      } else if(!hasForbid){
        msg = '@,# 금지단어입니다.';
      } else {
        msg = '';
      }
      return msg;
    },
    changePwd(){
      let msg = this.checkPwd(this.pwd1);
      if(msg === '') {
        msg ='비밀번호가 유효합니다.';
      }
      this.msgPwd1 = msg;
    },

      // if(this.pwdValue.length == 0){
      //   this.msgPwd = '비밀번호를 입력하세요';
      // } else if(pwdExp.test(this.pwdValue) == true){
      //   this.msgPwd = '';
      // }else{
      //   this.msgPwd = '숫자만 입력해주세요.';
      // }
      changePwd2(){
        let msg = this.checkPwd(this.pwd2);
        if(msg == ''){
            if(this.pwd1 === this.pwd2){
                msg='비밀번호확인이 일치합니다.';
            } else{
                msg='비밀번호확인이 일치하지 않습니다.'
            }
        }
        this.msgPwd2 = msg;
    },
      // 문자열 길이/ 문자 포함여부 / 숫자 포함여부 /금지어 포함여부/ 비번확인 일치여부
      // const pwdExp =  /^\d+$/; // 문자열이 숫자로만 구성되어야 함
      // if(this.pwdValue2.length == 0){
      //   this.msgPwd2 = '비밀번호 확인을 입력하세요';
      // } else if(pwdExp.test(this.pwdValue2) == true){
      //   this.msgPwd2 = '';
      // }else{
      //   this.msgPwd2 = '숫자만 입력해주세요.';
      // }
    changeCity(){
      switch(this.city){
        case '서울':
          this.message = '안녕하세요 반갑습니다';
          break;
          case '부산':
          this.message = '안녕하십니꺼 반갑습니더';
          break;
          case '대전':
          this.message = '안녕하셔유 반가워유';
          break;
          case '수원':
          this.message = '안녕하세요 반갑습니다';
          break;
          case '광주':
          this.message = '안녕하시오  반갑소잉';
          break;
          default:
            this.message = '안녕하세요 반갑습니다';
      }
    }
  },
};
</script>

<style scoped>

</style>