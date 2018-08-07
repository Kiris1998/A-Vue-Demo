<template>
    <div class="leftNav">
        <ul>
            <li>
                <i class="icon iconfont icon-fl-renminbi"></i>
                <div>结算</div>
            </li>
            <li>
                <i class="icon iconfont icon-dianpu"></i>
                 <div>店铺</div>
            </li>
            <li>
                <i class="icon iconfont icon-hanbao"></i>
                <div>商品</div>
            </li>
            <li>
                <i class="icon iconfont icon-huiyuanqia"></i>
                <div>会员</div>
            </li>
            <li>
                <i class="icon iconfont icon-kejian"></i>
                <div>设置</div>
            </li>
        </ul>
    </div>
</template>

<script>
export default{
  name: 'leftNav'
}
</script>

<style>
    .leftNav{
        color: #fff;
        font-size: 10px;
        height: 100%;
        background: #1D8ce0;
        float: left;
        width: 5%;
    }
    .leftNav ul{
        margin: 0;
        padding: 0;
    }
    .leftNav li{
        list-style: none;
        text-align: center;
        border-bottom:1px solid #20a0ff;
        padding: 10px;

    }
    @font-face {
    font-family: 'iconfont';  /* project id 781513 */
    src: url('//at.alicdn.com/t/font_781513_qi8886uiku.eot');
    src: url('//at.alicdn.com/t/font_781513_qi8886uiku.eot?#iefix') format('embedded-opentype'),
    url('//at.alicdn.com/t/font_781513_qi8886uiku.woff') format('woff'),
    url('//at.alicdn.com/t/font_781513_qi8886uiku.ttf') format('truetype'),
    url('//at.alicdn.com/t/font_781513_qi8886uiku.svg#iconfont') format('svg');
    }

    .iconfont {
    font-family:"iconfont" !important;
    font-size:25px;
    font-style:normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    }

    .icon-hanbao:before { content: "\e600"; }

    .icon-huiyuanqia:before { content: "\e638"; }

    .icon-zuanshi:before { content: "\e64c"; }

    .icon-dianpu:before { content: "\e666"; }

    .icon-kejian:before { content: "\e620"; }

    .icon-fl-renminbi:before { content: "\e634"; }

    .icon-shouji:before { content: "\e61a"; }

</style>
