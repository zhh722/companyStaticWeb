<template>
  <div class="product">
    <div class="nav">
      <navbar :current-type="currentType" @itemClick="itemClick"/>
    </div>
    <div class="list">
      <hight-light text="产品中心" bg-text="Product Center" :is-bg="true" id="title"/>
      <div class="productList">
        <ProductList :projects="currentList" img-height="260px"></ProductList>
      </div>
    </div>
  </div>
</template>

<script>
  import HightLight from "@/components/common/hightLight/HightLight";
  import Navbar from "@/views/product/navbar/Navbar";
  import ProductList from "@/components/common/productList/ProductList";
  import {product1,product2,product3, product4, product5, product6} from "@/assets/products";
import { pbkdf2 } from "crypto";

  export default {
    name: "Product",
    components: {HightLight, Navbar, ProductList},
    data() {
      return {
        product1,
        product2,
        product3,
        product4,
        product5,
        product6,
        currentType:'',
        currentList:null
      }
    },
    mounted(){
      this.currentType='齿轮'
      this.currentList=product1
    },
    methods:{
      itemClick(item) {
        switch (item) {
          case '齿轮':
            this.currentList = product1;
            this.currentType='齿轮';

            break;
          case '链轮':
            this.currentList = product2;
            this.currentType='链轮';
            break;
          case '齿条':
            this.currentList = product3;
            this.currentType='齿条';
            break;
          case '斜齿轮':
            this.currentList = product4;
            this.currentType='斜齿轮';
            break;
          case '伞齿轮':
            this.currentList = product5;
            this.currentType='伞齿轮';
            break;
          case '蜗轮蜗杆':
            this.currentList = product6;
            this.currentType='蜗轮蜗杆';
            break;
        }
      }
    }
  }
</script>

<style scoped>
  .product {
    display: flex;
    justify-content: center;
  }

  .list {
    width: 1200px;
    text-align: center;
  }

  .list p {
    font-size: 30px;
  }

  .nav {
    margin-top: 135px;
  }
  .productList{
    padding-left: 30px;
  }
  #title{
    padding-right: 210px;
  }
</style>
