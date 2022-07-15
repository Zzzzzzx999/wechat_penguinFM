<template>
  <div class="setting">
    <div class="functionalArea">
      <div class="functionalItem">
        <div class="itemLeft">
          <span>皮肤风格</span>
        </div>
        <div class="itemRight">
          <span>素雅白金</span>
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
    </div>
    <div class="functionalArea">
      <div class="functionalItem">
        <div class="itemLeft">
          <span>定时关闭</span>
        </div>
        <div class="itemRight">
          <span>已关闭</span>
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>音效设置</span>
        </div>
        <div class="itemRight">
          <span>无音效</span>
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>弹幕开关</span>
        </div>
        <div class="itemRight">
          <!-- <span>无音效</span>
          <image src="../static/icon/右箭.png"></image> -->
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>录音耳返</span>
        </div>
        <div class="itemRight">
          <!-- <span>无音效</span>
          <image src="../static/icon/右箭.png"></image> -->
        </div>
      </div>
    </div>
    <div class="functionalArea">
      <div class="functionalItem">
        <div class="itemLeft">
          <span>自动下载</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>清理缓存</span>
        </div>
        <div class="itemRight">
          <span>约33MB</span>
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
    </div>
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
        <div class="itemLeft">
          <span>通知</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>Siri捷径管理</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>双卡手机免流设置</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>Today小工具</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>车载电台</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>AI Toy</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
    </div>
    <div class="functionalArea">
      <div class="functionalItem">
        <div class="itemLeft">
          <span>喜欢,鼓励一下</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>帮助与反馈</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>我要当主播</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
      <div class="functionalItem">
        <div class="itemLeft">
          <span>关于</span>
        </div>
        <div class="itemRight">
          <image src="../static/icon/右箭.png"></image>
        </div>
      </div>
    </div>
    <div class="logOut">
      <span>退出登录</span>
    </div>
    <div class="footer" @click="goPlayer()">
      <div class="playBar">
        <div class="radioAvatar">
          <image src="../static/Picture_material/1657765591270.jpg"></image>
        </div>
        <div class="radioContent">
          <div class="radioContentHeader">
            <span>企鹅FM</span>
            </div>
          <div class="radioContentFooter">
              <span>随心一按 听点有趣</span>
          </div>
        </div>
        <div class="broadcast">
          <image src="../static/icon/homeIcon/24gf-playCircle.png"></image>
        </div>
        <div class="text">
          <image src="../static/icon/homeIcon/文件.png"></image>
        </div>
      </div>
      <!-- 进度条 -->
      <div class="progressBar" @click.stop>
        <slider class="slider" min="0" max="100" value="30" activeColor="#D3AB58" block-size="12"></slider>
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

<style lang="less">
.setting{
  font-size: 32rpx;
  font-weight: 500;
  position: relative;
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
      .itemLeft{
        width: 50%;
      }
      .itemRight{
        width: 50%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        color: darkgrey;
        font-size: 29rpx;
        image{
          width: 30rpx;
          height: 30rpx;
          margin-left: 20rpx;
        }
      }
    }
  }
  .logOut{
    width: 100%;
    height: 100rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 210rpx;
    span{
      color: #D3AB58;
    }
  }
  .footer{
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100vw;
    height: 210rpx;
    padding: 15rpx 0 60rpx;
    box-sizing: border-box;
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    background-color: #F9F9F9;
    .playBar{
      width: 100%;
      height: 130rpx;
      padding: 0 30rpx;
      box-sizing: border-box;
      display: flex;
      align-items: center;
      .radioAvatar{
        image{
          width: 100rpx;
          height: 100rpx;
          min-width: 100rpx;
          min-height: 100rpx;
          border-radius: 10rpx;
        }
      }
      .radioContent{
        height: 75%;
        display: flex;
        flex-flow: column nowrap;
        justify-content: space-around;
        flex-grow: 1;
        padding: 0 20rpx;
        .radioContentHeader{
          font-size: 36rpx;
          font-weight: 500;
        }
        .radioContentFooter{
          font-size: 28rpx;
          color: #D3AB58;
          background-clip: text;
          // -webkit-text-fill-color: #e7dabe;
          // -webkit-animation: slideShine 5s infinite;
        }
      }
      .broadcast{
        padding-right: 40rpx;
        image{
          width: 65rpx;
          height: 65rpx;
          min-width: 65rpx;
          min-height: 65rpx;
        }
      }
      .text{
        image{
          width: 65rpx;
          height: 65rpx;
          min-width: 65rpx;
          min-height: 65rpx;
        }
      }
    }
    .progressBar{
      height: 30rpx;
      width: 100vw;
      display: flex;
      align-items: center;
      .slider{
        width: 100%;
        margin: 0;
        vertical-align: center;
      }
      .wx-slider-thumb {
        display: none;
      }
    }
  }
}

</style>