<template>
  <div id="personal">
    <div class="personal-dh">
      <div @click="ht()"><van-icon name="arrow-left" /></div>
    </div>
    <div class="personal-img"><img src="../../assets/personal/1.png"/></div>
    <div class="personal-bj">{{stu.stuName}}</div>
    <div class="personal-body">
      <div><label>姓   名</label>：<input type="text" readonly :value="stu.stuName"></div>
      <div><label>开班时间</label>：<input type="text" readonly :value="stu.date"></div>
      <div>联系方式：<input type="text" :value="stu.email == '' || stu.email==null ? '暂无联系方式':stu.email"></div>
      <hr/>
      <div class="personal-textarea">
        <div>基本情况：</div>
        <textarea rows="3" cols="20">
       {{stu.detail}}
        </textarea>
      </div>
    </div>
  </div>
</template>

<script>
export default {
	data(){
		return{
			stu:{
				stuName:'',
				date:'',
				'email':'',
				'detail':''
			}
		}
	},
   methods: {
    ht(){
      this.$router.go(-1)
    }
  },mounted() {
  	this.stu.stuName = this.$route.query.stuName;
	this.stu.date = this.$route.query.date;
	this.stu.email = this.$route.query.email;
	this.stu.detail = this.$route.query.detail;
  }
}
</script>

<style scoped>
#personal{
  width: 100%;
  height: 100%;
  background: url("../../assets/personal/1.jpg") no-repeat;
  background-size: 110%;
  position: fixed;
  overflow: hidden;
  overflow-y: scroll;
}
.personal-dh{
  height: 60px;
  line-height: 60px;
  color: #fff;
  font-size: 30px;
  position: fixed;
  padding: 0 20px;
}
.personal-img{
  padding: 5px;
  border: 1px solid #fff;
  border-radius: 100%;
  width: 20%;
  margin: 15% auto 0 auto;
  display: flex;
  justify-content: center;
}
.personal-img>img{
  width: 80px;
  align-self:center;
}
.personal-bj{
  text-align: center;
  color: #fff;
  font-size: 18px;
  margin-top: 7%;
}
.personal-body{
  background: #fff;
  width: 80%;
  margin: 0 auto;
  box-sizing: border-box;
  padding: 20px 35px;
  margin-top: 15px;
  border-radius: 9px;
}
.personal-body>div{
  margin-bottom: 15px;
  font-size: 20px;
}
.personal-body>div>label{
  letter-spacing:12px;
}
.personal-body>div>input{
  width: 250px;
  border: 1px solid rgba(0, 0, 0, 0);
  border-bottom: 1px solid #ccc;
  height: 20px;
}
.personal-textarea{
  margin-top: 20px;
}
.personal-textarea>textarea{
  margin-top: 10px;
  width: 100%;
  height: 130px;
  border: 1px solid #ccb3e6;
  border-radius: 9px;
}
</style>