<template>
  <div>
    <!-- 데이터 불러오는 방법 -->
    <p>연세 IT 미래교육원</p>
    <!-- 머스태치 {{  }} -->
    <p>{{ title }}</p>
    <p v-text="title"></p>
    <p v-html="title"></p>
  </div>
</template>
<script>
export default{
  name:'TestVeiw',
  components:{},
  data(){
    return{
      title:'연세 IT <b>미래</b>교육원',
    }
  },
  methods:{},
}
</script>
<style scoped>
/* scoped는 다른파일x 같은파일 안에서만 적용 */
</style>
