<template>
    <div class="runningKnack">
        <div class="circle_process">
            <div class="wrapper">
                <div class="circle rightcircle">
                    <span>0</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name:'runningKnack',
  data() {
    return {
      property: 'value',
    };
  },
}
</script>

<style lang="less">
body {
    background-color: #222222;
    .runningKnack{
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        .circle_process {
            position: relative;
            width: 550rpx;
            height: 550rpx;
            margin-top: 30rpx;
            .wrapper {
                width: 100%;
                height: 70%;
                position: absolute;
                top: 0;
                left: 0;
                overflow: hidden;
                .circle{
                    width: 550rpx;
                    height: 550rpx;
                    border: 30rpx solid transparent;
                    border-radius: 50%;
                    position: absolute;
                    top: 0;
                    box-sizing: border-box;
                    // border-top: 30rpx solid #383838;
                    // border-right: 30rpx solid #383838;
                    // border-left: 30rpx solid #383838;
                    // border-bottom: 30rpx solid #383838;
                    border: 30rpx solid #383838;
                    left: 0;
                    color: white;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    font-size: 120rpx;
                }
            }
        }
    }
}
</style>