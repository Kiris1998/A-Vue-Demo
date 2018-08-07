<template>
    <div class="pos">
        <el-row>
            <el-col :span='7' class="order" :style="{height:orderHeight}">订单</el-col>
            <el-col :span='7'>商品</el-col>
        </el-row>
    </div>
</template>

<script>
export default{
  name: 'Pos',
  data () {
    return {
      orderHeight: ''
    }
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
</style>
