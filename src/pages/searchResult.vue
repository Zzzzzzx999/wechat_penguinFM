<template>
    <div class="searchResult">
        <div class="top">
            <div class="searchInput">
                <input type="text" v-model="searchValue" @confirm="beginSearch" placeholder="搜索节目/音乐/主播/广播">
                <image v-if="searchValue!=''" src="../static//icon/取消.png" @click="searchValue=''"></image>
            </div>
            <span @click="changePath('./home')">取消</span>
        </div>

    </div>
</template>

<script>
export default {
    name:'searchResult',
    data() {
        return {
            searchValue: '',
        };
    },
}
</script>

<style lang="less">
.top{
    height: 60rpx;
    display: flex;
    align-items: center;
    margin:20rpx 0 20rpx 40rpx;
    .searchInput{
        height: 100%;
        flex-grow: 1;
        display: flex;
        align-items: center;
        padding: 0 30rpx;
        background-color: rgba(226, 225, 225, 0.904);
        border-radius: 30rpx;
        input{
            flex: 1;
            height: 100%;
        }
        image{
            height: 40rpx;
            width: 40rpx;
            min-width: 40rpx;
            min-height: 40rpx;
        }
    }
    span{
        height: 100%;
        padding: 0 40rpx;
        color: gray;
        font-size: 36rpx;
    }
}
</style>