<template>
  <div >

    <div class="outsideDiv">
      <p class="item-detail-title-p">名称:{{goodItem.cigar_brand}}</p>
    </div>


    <div class="outsideDiv">
      <i-input :value.sync="goodItem.intro" class="changeInfoInput" type="textarea" :rows="10" placeholder="请输入..."></i-input>
    </div>

    <div class="btnDiv">
      <i-button @click="tijiaoAction" class="tijiaoBtn" type="success" long>确认提交</i-button>
      <i-button @click="cancleAction" class="tijiaoBtn" long>取消</i-button>
    </div>

    <Spin size="large" fix v-if="isLoading"></Spin>
  </div>
</template>

<script>
  import Search from '@/components/Search';
  import GoodsDetailNav from '@/components/nav/GoodsDetailNav';
  import ShopHeader from '@/components/header/ShopHeader';
  import ShowGoodsDetail from '@/components/goodsDetail/ShowGoodsDetail';
  import store from '@/vuex/store';
  import { mapState, mapActions } from 'vuex';
  export default {
    name: 'GoodsDetailChangeInfo',
    beforeRouteEnter (to, from, next) {
      window.scrollTo(0, 0);
      next();
    },
    created () {
      this.loadGoodsInfo();
      this.goodItem = JSON.parse(this.$route.query.goodItem);
    },
    data () {
      return {
        tagsColor: [ 'blue', 'green', 'red', 'yellow' ],
        goodItem:{}
      };
    },
    methods: {
      ...mapActions(['loadGoodsInfo']),

      tijiaoAction(){
        // this.$router.go(-1);
      },
      cancleAction(){
        this.$router.go(-1);
      }
    },
    computed: {
      ...mapState(['goodsInfo', 'isLoading'])
    },
    components: {
      Search,
      ShopHeader,
      GoodsDetailNav,
      ShowGoodsDetail
    },
    store
  };
</script>

<style scoped>
  .shop-item-path {
    height: 38px;
    background-color: rgb(236, 235, 235);
    line-height: 38px;
    color: #2c2c2c;
  }
  .shop-nav-container {
    margin: 0px auto;
    width: 80%;
  }
  .changeInfoInput{
    width: 70%;
    margin-top: 60px;
  }
  .outsideDiv{
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
  .tijiaoBtn{
    margin-left: 20px;
    width: 150px;
  }
  .btnDiv{
    margin-top: 40px;
    margin-right: 0;
    width: 100%;

    display: flex;
    flex-direction: row;
    justify-content: center;
  }
  .item-detail-title-p{
    margin-top: 40px;

    color: #333;
    font-size: 18px;
    font-weight:400
  }
</style>
