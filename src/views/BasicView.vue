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
    <h3>--------------------------속성연결-----------------------</h3>
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
    <h3>--------------------------제어문(v-for / v-if / v-else)-----------------------</h3>
    <div>
        <table>
            <thead>
                <tr>
                    <th>제품명</th>
                    <th>가격</th>
                    <th>카테고리</th>
                    <th>배송료</th>
                </tr>
            </thead>
            <tbody>
                <!-- v-for 데이터,순번 안에 products 배열 ,key값찾아서 배열 순회 -->
                <tr v-bind:key="index" v-for="(item,index) in products">
                    <td>{{item.name}}</td>
                    <td>{{item.price}}</td>
                    <td>{{item.category}}</td>
                    <td>{{item.delivery}}</td>
                </tr>
            </tbody>
        </table>
    </div>
    <div>
        <!-- v-if = 요소를 만드냐 안만드냐  -->
        <p v-if="true">if가 참일 때</p>
        <p v-if="false">if가 거짓일 때</p>
         <!-- v-show 보여주냐 안보여주냐 (display:none) -->
        <p v-show="true">show가 참일 때</p>
        <p v-show="false">show가 거짓일 때</p>
    </div>
    <h3>--------------------------이벤트(v-on / @)-----------------------</h3>
    <div>
        <button v-on:click="increaseCounter">click(증가)</button>
        <button @:click="decreaseCounter">click(감소)</button>
        <p>counter: {{counter}}</p>  
        <button @:click="increaseCounter(),showMsg()">증가 후 알림창</button>
        <button @:click="decreaseCounter(),showMsg()">감소 후 알림창</button>
        <br>
        <input type="number" v-model="countValue">  
        <button @:click="applyCounter">적용</button>
    </div>
    <div>
        <select v-model="cityValue" @change="changeCity">
            <option value="서울">서울</option>
            <option value="부산">부산</option>
            <option value="대구">대구</option>
            <option value="수원">수원</option>

        </select>
    </div>
    <br><br>
    <div>
        <input type="text" v-model="emailValue" @input="changeEnail" placeholder="이메일을 입력하세요">
        <p>{{emailValue}}</p>
        <p v-if="errEmail">{{errEmail}}</p>
    </div>
    <br>
    <div>
        <input type="text" v-model="pwdValue1" @input="changePwd1" placeholder="비밀번호를 입력하세요"><br>
        <input type="text" v-model="pwdValue2" @input="changePwd1" placeholder="비밀번호 확인을 입력하세요"><br>
        <p v-if="errPwd">{{errPwd}}</p>
    </div>
    <!-- 메소드 computed -->
    <div>
        <p>{{hello()}}</p>
        <p>{{hello()}}</p>
        <p>{{hello()}}</p>

        <p>{{hello2}}</p>
        <p>{{hello2}}</p>
        <p>{{hello2}}</p>
    </div>
    <div>
        성: <input type="text" v-model="lastName" @input="changeLastName"><br>
        이름: <input type="text" v-model="firstName" @input="changeFirstName"><br>
        <p>method:  {{ methodFullName() }}</p>
        <p>method:  {{ methodFullName() }}</p>
        <p>computed: {{ computeFullName }}</p>
        <p>computed: {{ computeFullName }}</p>
        <p>fullName: {{fullName}}</p>
        <p>fullName: {{fullName}}</p>
    </div>
    <!-- watch -->
    <div>
        <h4>유저정보 : {{userInfo}}</h4>
        <input type="text" v-model="userName">
        <input type="text" v-model="userAge">
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
      products: [
        {"name":"마우스","price":25000,"category":"PC용품","delivery":3000},
        {"name":"무선마우스","price":12000,"category":"PC용품","delivery":3000},
        {"name":"아이패드","price":725000,"category":"PC용품","delivery":3000},
        {"name":"태블릿거치대","price":32000,"category":"PC용품","delivery":3000},
      ],
    counter:0,
    countValue:10,
    cityValue:'수원',
    emailValue:'',
    errEmail:'',
    pwdValue1:'',
    pwdValue2:'',
    errPwd:'비밀번호를 입력하세요',
    lastName:'Go',
    firstName:'seungwon',
    fullName:'',
    userName:'홍길동',
    userAge:'30',
    userInfo:'',
    };
  },
  watch:{
    userName(){
        this.userInfo = this.userName+'('+this.userAge+')';
        },
        // userAge(){
        //   this.userInfo = this.userName+'('+this.userAge+')';
        // },
    },
computed: {
    hello2() {
        console.log('hello2 호출');
        return '안녕하세요, 반가워요';
    },
    computeFullName() {
        console.log('computeFullName 호출');
        return this.lastName + this.firstName;
    }
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
    increaseCounter(){
        this.counter = this.counter+1
    },
    decreaseCounter(){
        this.counter = this.counter-1
    },
    applyCounter(){
        this.countValue = this.counter
    },
    showMsg(){
        alert('현재값 :'+this.counter);
    },
    changeCity(){
        alert('선택하신 도시는 '+this.cityValue)
    },
    changeEnail(){
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        if( this.emailValue === '' || emailPattern.test(this.emailValue)){
            this.errEmail='';
            console.log('ok'+this.emailValue)
        }else{
            this.errEmail='email 형식에 어긋납니다';
            console.log('err'+this.emailValue)
        }
    },
    changePwd1(){
        if(this.pwdValue1===''){
            this.errPwd='비밀번호를 입력하세요';
        }else if(this.pwdValue2===''){
            this.errPwd='비밀번호 확인을 입력하세요';
        }else if(this.pwdValue1 === this.pwdValue2){
            this.errPwd='비밀번호가 일치합니다.'
        }else{
            this.errPwd='비밀번호가 일치하지 않습니다.';
        }
    },
    hello(){
        console.log ('hello()호출')
        return '안녕하세요, 반갑습니다.'
    },
       changeLastName() {
      // lastName 변경 시 fullName 업데이트
      console.log('changeLastName 호출');
      this.fullName = this.lastName + this.firstName;
    },
    changeFirstName() {
      // firstName 변경 시 fullName 업데이트
      console.log('changeFirstName 호출');
      this.fullName = this.lastName + this.firstName;
    },
    methodFullName() {
      // 메소드로 fullName 계산
      console.log('methodFullName 호출');
      return this.lastName + this.firstName;
    },
  }
};
</script>

<style scoped>
table{
    border-collapse: collapse;
    width: 100%;
}
td{
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
}
th{
    border: 1px solid #ddd;
    padding: 8px;
    font-weight: bold;
    text-align: center;
}
</style>