<template>
  <div class="setting">
    <div class="remind">
      <div class="remindItem">
        <span>2G/3G/4G网络下载提醒</span>
      </div>
      <div class="remindItem">
        <span>2G/3G/4G网络下载提醒</span>
      </div>
    </div>
    <div class="functionalArea">
      <div class="functionalItem">
        <span>通知</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>Siri捷径管理</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>双卡手机免流设置</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>Today小工具</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>车载电台</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>AI Toy</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
    </div>
    <div class="functionalArea">
      <div class="functionalItem">
        <span>喜欢,鼓励一下</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>帮助与反馈</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>我要当主播</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
      <div class="functionalItem">
        <span>关于</span>
        <image src="../static/icon/右箭.png"></image>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:"setting",
  data() {
    return {
      property: 'value',
    };
  },
  methods:{
    
  }
}
</script>

<style lang="less" scoped>
.setting{
  height: 100vh;
  width: 100vw;
  font-size: 27rpx;
  font-weight: 500;
  .remind{
    margin: 0 40rpx;
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    border-bottom: 1rpx solid #e9e7e7;
    .remindItem{
      height: 100rpx;
      width: 100%;
      display: flex;
      align-items: center;
    }
  }
  .functionalArea{
    display: flex;
    flex-flow: column nowrap;
    margin-top: 20rpx;
    border-bottom: 1rpx solid #e9e7e7;
    .functionalItem{
      height: 88rpx;
      width: 100%;
      padding: 0 40rpx;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      align-items: center;
      image{
        width: 30rpx;
        height: 30rpx;
      }
    }
  }
}
</style>