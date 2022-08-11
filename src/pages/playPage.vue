<template>
    <div class="playPage">
        <div class="playtop" :class="{'playMask':adjustSpeed,'vague':openDownload}">
            <image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
            <div class="user">
                <div class="number">
                    <span>11</span>
                </div>
                <image mode="aspectFill" src="https://img2.baidu.com/it/u=263031947,1647848730&fm=253&fmt=auto&app=138&f=JPEG?w=501&h=500"></image>
                <image mode="aspectFill" src="https://img0.baidu.com/it/u=3365573645,2073973856&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"></image>
            </div>
            <div class="functionalArea">
                <image mode="aspectFill" src="../static/icon/礼物.png" @click="changePath('../pages/gift')"></image>
                <image mode="aspectFill" src="../static/icon/消息.png"></image>
            </div>
        </div>
        <div class="playContent" :class="{'playMask':adjustSpeed}">
            <div class="progressBar" @click.stop>
                <slider class="slider" min="0" max="100" value="30" activeColor="#f1d498" block-color="#D3AB58" block-size="12"></slider>
                <div class="text">
                    <span>02:04</span>
                    <span>17:22</span>
                </div>
            </div>
            <div class="playService">
                <div class="playConfig">
                    <div class="definition configItem">
                        <span>高清</span>
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                    <div class="speakingSpeed configItem" @click="adjustSpeed=true">
                        <span>语速</span>
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                    <div class="order configItem">
                        <span>顺序</span>
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                </div>
                <div class="callSiri">
                    <image src="../static/Picture_material/1657979583074.jpg"></image>
                </div>
            </div>
            <div class="playControl">
                <image mode="aspectFill" id="changeTime" src="../static/icon/后退-22.png"></image>
                <image mode="aspectFill" id="cutSong" src="../static/icon/play-skip-back-circle.png"></image>
                <image mode="aspectFill" id="play" src="../static/icon/bg-suspend.png"></image>
                <image mode="aspectFill" id="cutSong" src="../static/icon/play-skip-forward-circle.png"></image>
                <image mode="aspectFill" id="changeTime" src="../static/icon/前进-22.png"></image>
            </div>
            <div class="programControl">
                <image :src="collect?'../static/icon/playPage/取消收藏.png':'../static/icon/playPage/取消收藏(1).png'" @click="collect=!collect"></image>
                <image src="../static/icon/playPage/排序.png" @click="openDownload=true,location('program')"></image>
                <image src="../static/icon/playPage/转发.png"></image>
                <image :src="timing?'../static/icon/playPage/广播-定时(1).png':'../static/icon/playPage/广播-定时.png'" @click="timing=!timing"></image>
                <image src="../static/icon/playPage/文本.png" @click="openDirectory=true,location('chapter')"></image>
            </div>
        </div>
        <div class="playPageTitle">
            <span>62从婴儿囚犯到皇帝</span>
            <image src="../static/icon/playPage/24gf-ellipsis.png"></image>
        </div>
        <!-- 调节语速 -->
        <div class="adjustSpeed" v-if="adjustSpeed">
           <div class="speed">
                 <div class="adjustTop">
                    <div class="title">
                        <span>调整语速</span>
                    </div>
                    <div class="progressBar">
                        <div class="speedDetail">
                            <div class="speedbox" :class="{'boxHidden':speed.one}">
                                <span>0.5x</span>
                            </div>
                            <div class="speedbox" :class="{'boxHidden':speed.two}">
                                <span>1.0x</span>
                            </div>
                            <div class="speedbox" :class="{'boxHidden':speed.three}">
                                <span>1.5x</span>
                            </div>
                            <div class="speedbox" :class="{'boxHidden':speed.four}">
                                <span>2.0x</span>
                            </div>
                        </div>
                        <slider class="slider" min="0" max="90" :value="sliderValue" 
                            activeColor="rgb(199, 199, 199)" block-color="#D3AB58" block-size="12" backgroundColor="rgba(222, 222, 222, 0.849)"
                            @change="changeSpeed">
                            <div class="box">
                                <div class="boxes"></div>
                                <div class="boxes"></div>
                                <div class="boxes"></div>
                            </div>
                            <div class="block" :class="{'speedOne':!speed.one,'speedTwo':!speed.two,'speedThree':!speed.three,'speedFour':!speed.four}">
                                <div class="blockItem"></div>
                            </div>
                        </slider>
                        <div class="sliderTime">
                            <span>0.5x</span>
                            <span>1.0x</span>
                            <span>1.5x</span>
                            <span>2.0x</span>
                        </div>
                    </div>
                </div>
                <div class="determine">
                    <span @click="adjustSpeed=false">确定</span>
                </div>
           </div>
        </div>
        <!-- 查看播放顺序 -->
        <div class="sequentialPlayBack" v-if="openDirectory">
            <div class="playBackDirectory">
                <div class="directoryTop">
                    <div class="directoryTopLeft">
                        <image src="../static/icon/playPage/23_顺序播放.png"></image>
                        <span>顺序播放(62集)</span>
                    </div>
                    <div class="directoryTopRight">
                        <image id="rightItem" src="../static/icon/playPage/保存顺序.png"></image>
                    <image id="rightItem" src="../static/icon/playPage/下载-文件下载-16.png"></image>
                    </div>
                </div>
                <scroll-view class="directoryContent" :scroll-y="true" :scroll-into-view="toViewChapter">
                    <view class="chapterItem" :class="{'activeChapterItem':chap.select}"
                        v-for="chap in chapters" :key="chap.id" @click="changeChapter(chap.id)" :id="'chapter'+chap.id">
                        <div class="chapterItemLeft">
                            <div class="chapterItemLeftTop">
                                <span>{{chap.name}}</span>
                            </div>
                            <div class="chapterItemLeftBottom">
                                <span>{{chap.duration}}</span><span id="separate">|</span>
                                <span>侯杨方</span><span id="separate">|</span>
                                <span>西汉盛世的启示</span>
                            </div>
                        </div>
                        <div class="chapterItemRight" @click.stop>
                            <image src="../static/icon/关闭.png" @click="deleteChapter(chap.id)"></image>
                        </div>
                    </view>
                </scroll-view>
                <div class="contentBottom" @click="changePath('./recentlyListened')">
                    <div class="contentBottomLeft">
                        <span>最近收听</span>
                    </div>
                    <div class="contentBottomRight">
                        <image src="../static/icon/homeIcon/右箭头.png"></image>
                    </div>
                </div>
                <div class="closeDirectory">
                    <span @click="openDirectory=false">关闭</span>
                </div>
            </div>
        </div>
        <!-- 查看下载列表 -->
        <div class="goDownload" v-if="openDownload">
        <!-- catchtouchmove禁止滚动 -->
            <div class="goDownloadTop">
                <div class="goDownloadTopLeft">
                    <image id="back" src="../static/icon/playPage/左箭.png" @click="openDownload=false"></image>
                    <image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
                </div>
                <div class="goDownloadTopRight">
                    <image src="../static/icon/playPage/取消收藏(white).png"></image>
                    <image src="../static/icon/playPage/排序(white).png"></image>
                    <image src="../static/icon/playPage/24gf-ellipsis.png"></image>
                </div>
            </div>
            <div class="goDownloadContentTitle">
                <div class="details contentTitleItem" v-for="content in contentTitle" :key="content.id"
                :class="{'activeContentTitleItem':content.select}" @click="changeContent(content.id)">
                    <span>{{content.name}}</span>
                    <span id="number">{{content.number}}</span>
                </div>
                <!-- <div class="details contentTitleItem">
                    <span>详情</span>
                </div>
                <div class="programs contentTitleItem" :class="{'activeContentTitleItem':openDownload}">
                    <span>节目</span>
                    <span id="number">62</span>
                </div>
                <div class="comments contentTitleItem">
                    <span>评论</span>
                    <span id="number">145</span>
                </div>
                <div class="makeLists contentTitleItem">
                    <span>打榜</span>
                </div> -->
            </div>
            <scroll-view class="goDownloadContentHidden" :class="{'goDownloadContent':contentTitle[1].select}" :scroll-y="true" :scroll-into-view="toViewProgram">
                <view class="programItem" v-for="program in programs" :key="program.id" @click="changeProgram(program.id)" :id="'program'+program.id"
                    v-show="contentTitle[1].select">
                    <div class="programItemLeft programItemBothSides">
                        <image src="../static/icon/playPage/添加.png"></image>
                    </div>
                    <div class="programItemMiddle">
                        <div class="programItemMiddleTop" :class="{'activeProgramItem':program.select}">
                            <span>{{program.name}}</span>
                        </div>
                        <div class="programItemMiddleBottom">
                            <span>播放</span><span>{{program.playBackVolume}}万</span><span id="separate">|</span>
                            <span>{{program.duration}}</span><span id="separate">|</span>
                            <span>{{program.time}}</span>
                        </div>
                    </div>
                    <div class="programItemRight programItemBothSides">
                        <image src="../static/icon/选择器展开.png"></image>
                    </div>
                </view>
            </scroll-view>
            <div class="goDownloadBottom" @click="goPlayer()">
                <div class="playBar">
                    <div class="radioAvatar">
                        <image mode="aspectFill" src="https://img0.baidu.com/it/u=1303479120,3193737549&fm=253&fmt=auto&app=138&f=JPEG?w=689&h=500"></image>
                    </div>
                    <div class="radioContent">
                        <div class="radioContentHeader">
                            <span>62从婴儿囚犯到皇帝</span>
                        </div>
                        <div class="radioContentFooter">
                            <span>左右滑动切换节目</span>
                        </div>
                    </div>
                    <div class="broadcast">
                        <image src="../static/icon/24gf-pauseCircle.png"></image>
                    </div>
                    <div class="text">
                        <image src="../static/icon/文件.png"></image>
                    </div>
                </div>
                <!-- 进度条 -->
                <div class="progressBar" @click.stop>
                    <slider class="slider" min="0" max="100" value="10" activeColor="#D3AB58" block-size="12"></slider>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"playPage",
    data() {
        return {
            collect: false,     //收藏
            timing:false,    //定时闹钟
            adjustSpeed:false,    //调整语速
            openDirectory:false, //打开播放目录
            openDownload:false, //打开下载列表
            sliderValue:30,     //滑块的值
            toViewChapter:'',
            toViewProgram:'',
            speed:{
                one:true,
                two:false,
                three:true,
                four:true,
            },
            contentTitle:[
                {id:1,name:'详情',number:'',select:false},
                {id:2,name:'节目',number:'62',select:true},
                {id:3,name:'评论',number:'145',select:false},
                {id:4,name:'打榜',number:'',select:false},
            ],
            chapters:[
                {id:9,name:'62从婴儿囚犯到皇帝',duration:'17:23',select:false},
                {id:8,name:'61海昏侯传奇',duration:'19:17',select:false},
                {id:7,name:'60盐铁会议: 一个至今未能解决在争论',duration:'16:02',select:false},
                {id:6,name:'59三驾马车的辅政团队',duration:'12:55',select:false},
                {id:5,name:'58汉武帝的评价 (下)',duration:'14:01',select:false},
                {id:4,name:'57汉武帝的评价 (上)',duration:'16:34',select:false},
                {id:3,name:'56顾命大计: 周公辅成王与花海遗诏',duration:'15:26',select:false},
                {id:2,name:'55千古一帝在悔悟: 不存在制造汉武帝',duration:'14:39',select:false},
                {id:1,name:'54婴儿囚犯',duration:'14:01',select:true},
            ],
            programs:[
                {id:23,name:'75海昏侯传奇',playBackVolume:'2.3',duration:'19:17',time:'2019.04.19',select:false},
                {id:22,name:'74盐铁会议: 一个至今未能解决在争论',playBackVolume:'2.5',duration:'16:02',time:'2019.04.15',select:false},
                {id:21,name:'73三驾马车的辅政团队',playBackVolume:'2.8',duration:'12:55',time:'2019.04.11',select:false},
                {id:20,name:'72汉武帝的评价 (下)',playBackVolume:'2.6',duration:'14:01',time:'2019.04.09',select:false},
                {id:19,name:'71汉武帝的评价 (上)',playBackVolume:'3.4',duration:'16:34',time:'2019.04.04',select:false},
                {id:18,name:'70顾命大计: 周公辅成王与花海遗诏',playBackVolume:'3.2',duration:'15:26',time:'2019.04.02',select:false},
                {id:17,name:'69千古一帝在悔悟: 不存在制造汉武帝',playBackVolume:'3.6',duration:'14:39',time:'2019.03.29',select:false},
                {id:16,name:'68从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:15,name:'67从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:14,name:'66从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:13,name:'65从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:12,name:'64从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:11,name:'63从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:10,name:'62从婴儿囚犯到皇帝',playBackVolume:'1',duration:'已听8%',time:'2019.04.23',select:false},
                {id:9,name:'61海昏侯传奇',playBackVolume:'2.3',duration:'19:17',time:'2019.04.19',select:false},
                {id:8,name:'60盐铁会议: 一个至今未能解决在争论',playBackVolume:'2.5',duration:'16:02',time:'2019.04.15',select:false},
                {id:7,name:'59三驾马车的辅政团队',playBackVolume:'2.8',duration:'12:55',time:'2019.04.11',select:false},
                {id:6,name:'58汉武帝的评价 (下)',playBackVolume:'2.6',duration:'14:01',time:'2019.04.09',select:false},
                {id:5,name:'57汉武帝的评价 (上)',playBackVolume:'3.4',duration:'16:34',time:'2019.04.04',select:false},
                {id:4,name:'56顾命大计: 周公辅成王与花海遗诏',playBackVolume:'3.2',duration:'15:26',time:'2019.04.02',select:false},
                {id:3,name:'55千古一帝在悔悟: 不存在制造汉武帝',playBackVolume:'3.6',duration:'14:39',time:'2019.03.29',select:false},
                {id:2,name:'54婴儿囚犯',playBackVolume:'3.7',duration:'14:01',time:'2019.03.25',select:false},
                {id:1,name:'53汉武帝与太子微妙的关系',playBackVolume:'4.0',duration:'16:55',time:'2019.03.21',select:true},
            ]
        };
    },
    methods: {
        changePath(path){
            wx.navigateTo({url:path})
        },
        backPath(){
            wx.navigateBack({delta:1})
        },
        changeSpeed(e){
            setTimeout(() => {
                
                if (e.detail.value<15) {
                    this.sliderValue = 0
                    this.speedGetTrue()
                    this.speed.one=false
                    console.log(111, e.detail.value);
                }else if(e.detail.value>=15 && e.detail.value<45){
                    this.sliderValue = 30
                    this.speedGetTrue()
                    this.speed.two=false
                    console.log(222, e.detail.value);
                }else if(e.detail.value>=45 && e.detail.value<75){
                    this.sliderValue = 60
                    this.speedGetTrue()
                    this.speed.three=false
                    console.log(333, e.detail.value);
                }else{
                    this.sliderValuel = 90
                    this.speedGetTrue()
                    this.speed.four=false
                    console.log(444, e.detail.value);
                    console.log(this.sliderValuel);
                }
            }, 1000);
            // console.log(this.sliderValue);
        },
        speedGetTrue(){
            this.speed.one=true
            this.speed.two=true
            this.speed.three=true
            this.speed.four=true
        },
        changeContent(id){
            for (let a = 0; a < this.contentTitle.length; a++) {
                this.contentTitle[a].select = false
            }
            this.contentTitle[id-1].select = true
        },
        changeChapter(Id){
            for (let i = 0; i < this.chapters.length; i++) {
                this.chapters[i].select = false
            }
            for (let i = 0; i < this.chapters.length; i++) {
                if (this.chapters[i].id == Id) {
                    this.chapters[i].select=true
                }
            }
        },
        changeProgram(id){
            for (let p = 0; p < this.programs.length; p++) {
                this.programs[p].select = false
            }
            for (let p = 0; p < this.programs.length; p++) {
                if (this.programs[p].id==id) {
                    this.programs[p].select = true
                }
            }
        },
        deleteChapter(id){
            var new_arr=[]
            // arr=this.chapters.splice(id-1,1)
            // this.chapters.filter((item)=>{
            //     return item.id != id
            // })
            for (let i = 0; i < this.chapters.length; i++) {
                // const element = array[i];
                if (this.chapters[i].id != id) {
                    new_arr.push(this.chapters[i])
                }
            }
            this.chapters = new_arr
        },
        goPlayer(){
            // const backgroundAudioManager = wx.getBackgroundAudioManager()
            // backgroundAudioManager.title =  '西汉盛世的启示'
            // backgroundAudioManager.singer = '侯杨方'
            // backgroundAudioManager.src = 'http://music.163.com/song/media/outer/url?id=447925558.mp3'
            // backgroundAudioManager.coverImgUrl = 'https://i0.hdslb.com/bfs/music/3e0cfc04de84ce6176c18bb92394a1b5efa57978.jpg@370w_370h.webp'
            wx.navigateTo({url:'../pages/playPage'})
        },
        location(p){
            if (p=='chapter') {
                for (let i = 0; i < this.chapters.length; i++) {
                    if (this.chapters[i].select===true) {
                        this.toViewChapter = p+this.chapters[i].id
                        console.log('此时选中',this.toViewChapter);
                    }
                }
            }else if (p=='program') {
                for (let i = 0; i < this.programs.length; i++) {
                    if (this.programs[i].select===true) {
                        this.toViewProgram = p+this.programs[i].id
                        console.log('此时选中',this.toViewProgram);
                    }
                }
            }
        }
    }
}
</script>

<style lang="less">
.playPage{
    height: 100vh;
    width: 100vw;
    position: relative;
    .playtop{
        height: 53vh;
        width: 100vw;
        position: relative;
        image{
            height: 100%;
            width: 100%;
            filter: brightness(80%);
        }
        .user{
            height: 170rpx;
            width: 60rpx;
            position: absolute;
            top: 50%;
            right: 5%;
            transform: translate(0,-100%);
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            justify-content: space-around;
            .number{
                font-size: 25rpx;
                color: white;
            }
            image{
                height: 50rpx;
                width: 50rpx;
                border-radius: 50%;
            }
        }
        .functionalArea{
            height: 150rpx;
            width: 60rpx;
            position: absolute;
            top: 75%;
            right: 5%;
            transform: translate(0,-15%);
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            justify-content: space-around;
            image{
                height: 50rpx;
                width: 50rpx;
            }
        }
    }
    .playContent{
        height: 47vh;
        display: flex;
        flex-flow: column nowrap;
        .progressBar{
            height: 20rpx;
            width: 100vw;
            display: flex;
            flex-flow: column nowrap;
            justify-content: center;
            .slider{
                height: 35rpx;
                width: 100%;
                margin: 0;
                vertical-align: center;
            }
            .wx-slider-thumb {
                border-radius: 0;
            }
            .wx-slider-handle-wrapper{
                height: 20rpx;
            }
            .text{
                margin: 0 30rpx;
                display: flex;
                justify-content: space-between;
                color: rgb(160, 158, 158);
                font-size: 25rpx;
            }
        }
        .playService{
            padding-left: 50rpx;
            margin-top: 100rpx;
            height: 60rpx;
            display: flex;
            justify-content: center;
            align-items: center;
            .playConfig{
                flex-grow: 1;
                height: 60rpx;
                display: flex;
                justify-content: center;
                align-items: center;
                .configItem{
                    margin: 7rpx;
                    height: 35rpx;
                    width: 85rpx;
                    border: 2rpx solid gray;
                    border-radius: 20rpx;
                    font-size: 23rpx;
                    color: rgb(165, 164, 164);
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    image{
                        height: 25rpx;
                        width: 25rpx;
                    }
                }
            }
            .callSiri{
                height: 60rpx;
                width: 60rpx;
                border-bottom-left-radius: 30rpx;
                border-top-left-radius: 30rpx;
                display: flex;
                align-items: center;
                justify-content: center;
                padding-right: 10rpx;
                background-color: rgb(235, 221, 221);
                image{
                    width: 35rpx;
                    height: 35rpx;
                    border-radius: 50%;
                }
            }
        }
        .playControl{
            height: 150rpx;
            display: flex;
            justify-content: space-around;
            align-items: center;
            margin: 80rpx 30rpx;
            #changeTime{
                height: 50rpx;
                width: 50rpx;
            }
            #cutSong{
                height: 70rpx;
                width: 70rpx;
            }
            #play{
                height: 130rpx;
                width: 130rpx;
            }
        }
        .programControl{
            margin: 50rpx 13rpx 0;
            display: flex;
            justify-content: space-around;
            align-items: center;
            image{
                height: 40rpx;
                width: 40rpx;
            }
        }
    }
    .playPageTitle{
        width: 100%;
        position: absolute;
        top: 80rpx;
        left: 0rpx;
        padding: 0 40rpx;
        box-sizing: border-box;
        font-size: 42rpx;
        font-weight: 500;
        color: aliceblue;
        z-index: 1;
        display: flex;
        justify-content: space-between;
        image{
            height: 50rpx;
            width: 50rpx;
        }
    }
    .adjustSpeed{
        position: fixed;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
        display: flex;
        align-items: flex-end;
		background: rgba(0, 0, 0, 0.45);
        z-index: 7;
        .speed{
            height: 30vh;
            width: 100vw;
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            background: #f0f0f0;
            z-index: 8;
            .adjustTop{
                height: 62%;
                width: 100vw;
                background-color: white;
                display: flex;
                flex-flow: column nowrap;
                align-items: center;
                .title{
                    height: 100rpx;
                    width: 100%;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    font-size: 25rpx;
                    color: rgb(165, 164, 164);
                }
                .progressBar{
                    height: 30rpx;
                    width: 90vw;
                    display: flex;
                    flex-flow: column nowrap;
                    justify-content: center;
                    align-items: center;
                    margin-top: 50rpx;
                    .speedDetail{
                        display: flex;
                        justify-content: space-between;
                        width: 100vw;
                        padding: 0 20rpx;
                        box-sizing: border-box;
                        .speedbox{
                            height: 60rpx;
                            width: 90rpx;
                            background-color: rgba(243, 233, 233, 0.849);
                            border-radius: 20rpx;
                            margin-bottom: 20rpx;
                            color: #e0ac42;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                        }
                        .boxHidden{
                            visibility:hidden;
                        }
                        .blockhidden{
                            background-color: white;
                        }
                    }
                    .slider{
                        width: 95%;
                        margin: 0;
                        vertical-align: center;
                        position: relative;
                        .box{
                            z-index: -1;
                            position: absolute;
                            top: 8rpx;
                            left: 3rpx;
                            height: 10rpx;
                            width:100%;
                            display: flex;
                            justify-content: space-between;
                            .boxes{
                                height: 16rpx;
                                width: 33.33%;
                                border-left: 3rpx solid rgb(173, 169, 169);
                                z-index: -5;
                            }
                            .boxes:last-child{
                                border-right: 3rpx solid rgb(173, 169, 169);
                            }
                        }
                        .block{
                            height: 25rpx;
                            width: 25rpx;
                            position: absolute;
                            top: 7rpx;
                            left: 0;
                            display: flex;
                            justify-content: space-between;
                            border-radius: 50%;
                            background-color: #D3AB58;
                            .blockItem{
                                height: 100%;
                                width: 100%;
                            }
                        }
                        .speedOne{
                            left: 0;
                        }
                        .speedTwo{
                            left:205rpx;
                        }
                        .speedThree{
                            left:410rpx;
                        }
                        .speedFour{
                            left:615rpx;
                        }
                    }
                    .wx-slider-thumb {
                        display: none;
                    }
                    .sliderTime{
                        display: flex;
                        width: 100%;
                        justify-content: space-between;
                        font-size: 20rpx;
                        padding: 0 10rpx;
                        color: grey;
                    }
                }
            }
        }
        .determine{
            flex-grow: 1;
            width: 100vw;
            display: flex;
            align-content: center;
            justify-content: center;
            background-color: white;
            margin-top: 20rpx;
            span{
                font-size: 32rpx;
                font-weight: 600;
                margin-top: 30rpx;
            }
        }
        
    }
    .sequentialPlayBack{
        position: fixed;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
        background-color: rgba(0, 0, 0, .45);
        display: flex;
        align-items: flex-end;
        z-index: 3;
        .playBackDirectory{
            height: 75vh;
            width: 100vw;
            background: whitesmoke;
            display: flex;
            flex-flow: column nowrap;
            .directoryTop{
                height: 80rpx;
                width: 100%;
                display: flex;
                padding: 0 40rpx;
                box-sizing: border-box;
                background-color: white;
                .directoryTopLeft{
                    height: 100%;
                    width: 50%;
                    display: flex;
                    align-items: center;
                    image{
                        height: 35rpx;
                        width: 35rpx;
                    }
                    span{
                        padding-left: 20rpx;
                        font-size: 30rpx;
                        font-weight: 500;
                    }
                }
                .directoryTopRight{
                    height: 100%;
                    width: 50%;
                    display: flex;
                    align-items: center;
                    justify-content: flex-end;
                    image{
                        height: 35rpx;
                        width: 35rpx;
                        padding-left: 50rpx;
                    }
                }
            }
            .directoryContent{
                flex-grow: 1;
                padding-top: 10rpx;
                flex-flow: column-reverse nowrap;
                justify-content: flex-end;
                background-color: white;
                overflow: scroll;
                .chapterItem{
                    display: flex;
                    align-items: center;
                    padding: 0 40rpx;
                    box-sizing: border-box;
                    margin-bottom: 25rpx;
                    letter-spacing: 2rpx;
                    .chapterItemLeft{
                        flex-grow: 1;
                        height: 75rpx;
                        display: flex;
                        flex-flow: column nowrap;
                        justify-content: space-between;
                        .chapterItemLeftTop{
                            font-size: 26rpx;
                            font-weight: 600;
                        }
                        .chapterItemLeftBottom{
                            color: rgb(163, 161, 161);
                            font-size: 21rpx;
                            font-weight: 400;
                            #separate{
                                margin: 0 12rpx;
                            }
                        }
                    }
                    .chapterItemRight{
                        height: 75rpx;
                        width: 35rpx;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        image{
                            height: 25rpx;
                            width: 25rpx;
                            min-height: 25rpx;
                            min-width: 25rpx;
                        }
                    }
                }
                .activeChapterItem{
                    border-left:5rpx solid #e0ac42;
                    .chapterItemLeftTop{
                        color: #e0ac42;
                    }
                }
            }
            .contentBottom{
                display: flex;
                align-items: center;
                padding: 0 40rpx;
                box-sizing: border-box;
                height: 50rpx;
                width: 100%;
                background-color: white;
                .contentBottomLeft{
                    flex-grow: 1;
                    font-size: 25rpx;
                    color: rgb(163, 161, 161);
                }
                .contentBottomRight{
                    height: 75rpx;
                    width: 35rpx;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    image{
                        height: 25rpx;
                        width: 25rpx;
                        min-height: 25rpx;
                        min-width: 25rpx;
                    }
                }
            }
            .closeDirectory{
                height: 160rpx;
                width: 100%;
                padding: 0 30rpx 60rpx;
                margin: 20rpx 0 0;
                box-sizing: border-box;
                display: flex;
                justify-content: center;
                align-items: center;
                background-color: white;
                font-size: 28rpx;
                font-weight: 600;
            }
        }
    }
    .goDownload{
        position: fixed;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
        z-index: 3;
        display: flex;
        flex-flow: column nowrap;
        .goDownloadTop{
            height: 100rpx;
            width: 100%;
            background: rgba(0, 0, 0,.65);
            padding: 0 30rpx;
            box-sizing: border-box;
            display: flex;
            .goDownloadTopLeft{
                width: 50%;
                height: 100%;
                display: flex;
                align-items: center;
                margin-top: 5px;
                #back{
                    width: 40rpx;
                    height: 40rpx;
                    padding: 0;
                }
            }
            .goDownloadTopRight{
                width: 50%;
                height: 100%;
                display: flex;
                justify-content: flex-end;
                align-items: center;
                margin-top: 5px;
            }
            image{
                height: 50rpx;
                width: 50rpx;
                padding-left: 30rpx;
            }
        }
        .goDownloadContentTitle{
            height: 70rpx;
            width: 100%;
            background-color: white;
            padding: 0 80rpx;
            box-sizing: border-box;
            display: flex;
            justify-content: space-around;
            align-items: center;
            font-size: 30rpx;
            font-weight: 600;
            flex-shrink: 0;
            .contentTitleItem{
                height: 50rpx;
                width: 85rpx;
                position: relative;
                #number{
                    height: 20rpx;
                    width: 30rpx;
                    position: absolute;
                    top: -3rpx;
                    right: -7rpx;
                    font-size: 18rpx;
                }
            }
            .activeContentTitleItem{
                span{
                    color: #D3AB58;
                    border-bottom: 5rpx solid #D3AB58;
                }
                #number{
                    border-bottom: 0rpx;
                }
            } 
        }
        .goDownloadContent{
            flex-grow: 1;
            width: 100%;
            background-color: white;
            padding: 25rpx 30rpx;
            box-sizing: border-box;
            overflow: scroll;
            // display: flex;
            // flex-flow: column-reverse nowrap;
            .programItem{
                display: flex;
                align-items: center;
                height: 70rpx;
                margin: 0rpx 15rpx 40rpx;
                .programItemBothSides{
                    width: 35rpx;
                    height: 35rpx;
                    image{
                        width: 35rpx;
                        height: 35rpx;
                        min-width: 35rpx;
                        min-height: 35rpx;
                    }
                }
                .programItemMiddle{
                    height: 100%;
                    flex-grow: 1;
                    display: flex;
                    flex-flow: column nowrap;
                    justify-content: space-between;
                    padding-left: 20rpx;
                    .programItemMiddleTop{
                        font-size: 27rpx;
                        font-weight: 600;
                    }
                    .programItemMiddleBottom{
                        font-size: 23rpx;
                        font-weight: 400;
                        color: rgb(173, 169, 169);
                        #separate{
                            padding: 0 12rpx;
                        }
                    }
                }
            }
            .activeProgramItem{
                color: #D3AB58;
            }
        }
        // 隐藏下载目录文本
        .goDownloadContentHidden{
            flex-grow: 1;
            width: 100%;
            background-color: white;
        }
        .goDownloadBottom{
            height: 200rpx;
            width: 100%;
            background-color: #F9F9F9;
            padding: 15rpx 0 60rpx;
            box-sizing: border-box;
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            background-color: #F9F9F9;
            z-index: 3;
            .playBar{
                width: 100%;
                height: 130rpx;
                padding: 0 30rpx;
                box-sizing: border-box;
                display: flex;
                align-items: center;
                .radioAvatar{
                    image{
                        width: 75rpx;
                        height: 75rpx;
                        min-width: 75rpx;
                        min-height: 75rpx;
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
                        font-size: 30rpx;
                        font-weight: 600;
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
                        width: 50rpx;
                        height: 50rpx;
                        min-width: 50rpx;
                        min-height: 50rpx;
                    }
                }
                .text{
                    image{
                        width: 50rpx;
                        height: 50rpx;
                        min-width: 50rpx;
                        min-height: 50rpx;
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
}
.vague{
    filter: blur(40rpx);
}
</style>