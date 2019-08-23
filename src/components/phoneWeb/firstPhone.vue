<template>
    <div class="divAll">
      <Row type="flex" justify="space-between" class="code-row-bg">
        <i-col span="6"><img class="iconStyle" /></i-col>
        <i-col span="6"></i-col>
        <i-col span="6"></i-col>
        <i-col span="6"><img class="moreStyle" @click="jumpSecondVC"/></i-col>
      </Row>

      <div class="secondDiv">
        <div class="textStyle textStyle1">蓝皮书</div>
        <div class="textStyle textStyle2" >记录分享美好生活</div>
        <div class="textStyle textStyle3">If youlove life,life will love your back</div>
      </div>
    </div>

</template>

<script>
    export default {
        name: "firstPhone",
      methods:{
        jumpSecondVC(){
          this.$router.push('/');
        }
      }
    }
</script>

<style scoped>

.divAll{

  background: url('https://github.com/xxz888/YX_YueTa/blob/master/homebj.png?raw=true') center center no-repeat;
  background-size: 100% 100%;
  height: 100%;
  width: 100%
}
.iconStyle{
  width:163px;
  height:50px;
  background: url('https://github.com/xxz888/YX_YueTa/blob/master/homeicon.png?raw=true') center center no-repeat;
  background-size: 100% 100%;
}
.moreStyle{
  width:44px;
  height:44px;
  background: url('https://github.com/xxz888/YX_YueTa/blob/master/homemore.png?raw=true') center center no-repeat;
  background-size: 100% 100%;

}
.firstDiv{
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
}
.secondDiv{
  margin-top:250px ;
  width: 100%;
  height: 500px;
}
.textStyle{
  text-align: center;
  color: #fff;
}
.textStyle1{
  height:calc(72/640*100%);
  font-size:65px;
  font-weight:700;

}
.textStyle2{
  margin-top: 44px;
  height:60px;
  font-size:48px;
  font-family:PingFang SC;
  font-weight:400;
  color:rgba(255,255,255,1);
}
.textStyle3{
  margin-top: 24px;
  height:30px;
  font-size:20px;
  font-family:Arial;
  font-weight:normal;
  color:rgba(255,255,255,1);
}
</style>
