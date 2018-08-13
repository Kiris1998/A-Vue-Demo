/* eslint-disable */
<template>
    <div class="pos">
        <el-row>
            <el-col :span='7' class="order" :style="{height:orderHeight}">
                <el-tabs class="tabs">
                    <el-tab-pane label="点餐">
                        <el-table border :data="tableData">
                            <el-table-column prop="goodsName" label="商品">

                            </el-table-column>
                             <el-table-column prop="count" label="数量">

                            </el-table-column>
                             <el-table-column prop="price" label="金额">

                            </el-table-column>
                            <el-table-column label="操作">
                                <template slot-scope="scope">
                                    <el-button type="text" size="small">增加</el-button>
                                    <el-button type="text" size="small">删除</el-button>
                                </template>
                            </el-table-column>
                        </el-table>
                        <div class="btns">
                            <el-button type="warning" >挂单</el-button>
                            <el-button type="danger" >删除</el-button>
                            <el-button type="success" >结账</el-button>
                        </div>
                    </el-tab-pane>
                    <el-tab-pane label="挂单">价格</el-tab-pane>
                    <el-tab-pane label="外卖">数量</el-tab-pane>
                </el-tabs>
            </el-col>
            <el-col :span='17'>
                <div class="often-goods">
                    <div class="title">常用商品</div>
                    <div class="often-goods-list">
                        <ul>
                            <li v-for="item in oftenGoods" :key="item.goodId">
                                <span>{{item.goodsName}}</span>
                                <span class="o-price">￥{{item.price}}元</span>
                            </li>
                        </ul>
                    </div>
                    <div class="good-type">
                        <el-tabs>
                            <el-tab-pane label="汉堡">
                                <ul class='cookList'>
                                    <li v-for="item in type0Goods" :key="item.goodsId">
                                        <span class="foodImg"><img :src="item.goodsImg" width="100%"></span>
                                        <span class="foodName">{{item.goodsName}}</span>
                                        <span class="foodPrice">￥{{item.price}}元</span>
                                    </li>
                                </ul>
                            </el-tab-pane>
                            <el-tab-pane label="小食">
                                <ul class='cookList'>
                                    <li v-for="item in type1Goods" :key="item.goodsId">
                                        <span class="foodImg"><img :src="item.goodsImg" width="100%"></span>
                                        <span class="foodName">{{item.goodsName}}</span>
                                        <span class="foodPrice">￥{{item.price}}元</span>
                                    </li>
                                </ul>
                            </el-tab-pane>
                            <el-tab-pane label="饮料">
                                <ul class='cookList'>
                                    <li v-for="item in type2Goods" :key="item.goodsId">
                                        <span class="foodImg"><img :src="item.goodsImg" width="100%"></span>
                                        <span class="foodName">{{item.goodsName}}</span>
                                        <span class="foodPrice">￥{{item.price}}元</span>
                                    </li>
                                </ul>
                            </el-tab-pane>
                            <el-tab-pane label="套餐">
                                <ul class='cookList'>
                                    <li v-for="item in type3Goods" :key="item.goodsId">
                                        <span class="foodImg"><img :src="item.goodsImg" width="100%"></span>
                                        <span class="foodName">{{item.goodsName}}</span>
                                        <span class="foodPrice">￥{{item.price}}元</span>
                                    </li>
                                </ul>
                            </el-tab-pane>
                        </el-tabs>
                    </div>
                </div>
            </el-col>
        </el-row>
    </div>
</template>

<script>
import axios from 'axios'
export default{
  name: 'Pos',
  data () {
    return {
      orderHeight: '',
      tableData: [],
      oftenGoods: [],
      type0Goods: [],
      type1Goods: [],
      type2Goods: [],
      type3Goods: []
    }
  },
  created: function () {
    axios.get('http://jspang.com/DemoApi/oftenGoods.php')
      .then(res => {
        this.oftenGoods = res.data
      })
      .catch(err => {
        console.log(err)
      })
    axios.get('http://jspang.com/DemoApi/typeGoods.php')
      .then(res => {
        this.type0Goods = res.data[0]
        this.type1Goods = res.data[1]
        this.type2Goods = res.data[2]
        this.type3Goods = res.data[3]
      })
  },
  mounted: function () {
    this.orderHeight = document.body.clientHeight + 'px'
  }
}
</script>

<style scoped>
    .order{
        background: #f9fafc;
        border-right: solid 1px #C0CCDA;
    }
    .tabs{
        padding:5px;
    }
    .btns{
        margin-top: 15px;
    }
    .title{
       height: 20px;
       border-bottom:1px solid #D3DCE6;
       background-color: #F9FAFC;
       padding:10px;
    }
    .often-goods-list ul li{
      list-style: none;
      float:left;
      border:1px solid #E5E9F2;
      padding:10px;
      margin:5px;
      background-color:#fff;
    }
   .o-price{
      color:#58B7FF;
    }
   .good-type{
       clear: both;
       padding: 10px;
    }
   .cookList li{
       list-style: none;
       width:23%;
       border:1px solid #E5E9F2;
       height: auot;
       overflow: hidden;
       background-color:#fff;
       padding: 15px;
       float:left;
       margin: 2px;
       border-radius: 7%;
    }
   .cookList li span{
        display: block;
        float:left;
    }
   .foodImg{
       width: 40%;
       border-radius: 10px;
    }
   .foodName{
       font-size: 18px;
       padding-left: 10px;
       color:brown;
    }
   .foodPrice{
       font-size: 16px;
       padding-left: 10px;
       padding-top:10px;
    }
</style>
