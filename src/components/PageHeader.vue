<template>
<h1 class="h1">
    <a href="#">
        <span class="h1__primary">微信广告</span>
        <span class="h1__secondary">数字字体测试 0.0.1</span>
    </a>
</h1>
</template>

<script>
export default {
  data() {
    return {
    }
  },
  components: {
  }
};
</script>
<style lang="less">
.h1{
    margin-top: 10px;
    margin-bottom: 61px;
    font-family:
        -apple-system, BlinkMacSystemFont,
        "Segoe UI", Roboto, "Helvetica Neue", Helvetica,
        "PingFang SC", Arial, "Hiragino Sans GB", "Microsoft YaHei",
        sans-serif;
    font-size: 14px;
    line-height: 56px;
    border-bottom: 1px solid #E0E0E0;

    a{
        display: block;
        max-width: 650px;
        margin: 0 auto;
    }
}
.h1__primary{
    position: relative;
    margin-right: 16px;
    color: #757575;

    &::after{
        content: "";
        position: absolute;
        top: 2px;
        right: -10px;
        width: 1px;
        height: 14px;
        background: #A6A6A6;
    }
}
.h1__secondary{
    color: #545454;
    font-weight: 600;
}
</style>
