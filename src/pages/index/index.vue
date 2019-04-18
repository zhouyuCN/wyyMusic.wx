<template>
  <div>
    <!-- 头部 -->
    <div class="header">
      <a href="#" class="logo" hover-class="none">
        <img src="../../../static/images/logo.png" alt>
        <span>网易云音乐</span>
      </a>
      <a href="#" class="down" hover-class="none">
        <button plain="true">下载APP</button>
      </a>
    </div>
    <!-- tab -->
    <div class="test">
      <div class="testNav">
        <div :class="{'selected':tab === 1,'testTitle':true}" @click="changTab(1)">推荐音乐</div>
        <div :class="{'selected':tab === 2,'testTitle':true}" @click="changTab(2)">热歌榜</div>
        <div :class="{'selected':tab === 3,'testTitle':true}" @click="changTab(3)">搜索</div>
      </div>
      <!-- tab 内容 -->
      <div class="content">
        <!-- 热歌榜单 -->
        <div v-if="tab===1" class="recommend">
          <div class="title">
            <span>|</span>
            <h2>推荐歌单</h2>
          </div>
          <!-- 音乐 -->
          <div class="recommend-box">
            <a href="/pages/playlist/main" class="item" v-for="(item,index) in recomMusicList" :key="index">
              <div class="item-img">
                <img :src="item.picUrl" alt>
                <div class="hits">
                  <span>@</span>
                  <span>{{item.playCount}}万</span>
                </div>
              </div>
              <p>&nbsp&nbsp{{item.name}}</p>
            </a>
          </div>
          <!-- 最新音乐 -->
          <div class="title">
            <span>|</span>
            <h2>最新音乐</h2>
          </div>
          <!-- 音乐 -->
          <div class="new-music-box">
            <div class="new-music-item" v-for="(item,index) in newMusic" :key="index">
              <div class="new-music-name">
                <p>{{item.name}}</p>
                <p class="singer">
                  <span>@</span>
                  <span>{{item.song.artists[0].name}}-{{item.song.album.alias[0]}}</span>
                </p>
              </div>
              <div class="play">
                <a href="#" hover-class="none">
                  <span class="iconfont icon-bofang" ></span>
                </a>
              </div>
            </div>
          </div>
          <!-- 底部 -->
          <div class="foot">
            <div class="foot-box">
              <div class="logo">
                <a href="#">
                  <img src="../../../static/images/logo.png" alt>
                  <span>网易云音乐</span>
                </a>
              </div>
              <button plain="true">打开App,发现更多好音乐 ></button>
              <p>网易公司版权所有©1997-2019 杭州乐读科技有限公司运营</p>
            </div>
          </div>
        </div>
        <div v-else-if="tab===2" class="m-hmhot">
          <div class="hot-top">
            <div class="hot-icon">
              <img
                src="//s3.music.126.net/m/s/img/index_icon_2x.png?5207a28c3767992ca4bb6d4887c74880"
                alt
              >
            </div>
            <p class="hot-time">更新日期: 04月11日</p>
          </div>
          <!-- 音乐排行 -->
          <div class="hot-music-box">
            <!-- 音乐 -->
            <div class="hot-music-item">
              <!--名次 -->
              <div class="music-num">01</div>
              <div class="music-content">
                <div class="hot-music-name">
                  <p>神秘嘉宾</p>
                  <p class="singer">
                    <span>@</span>
                    <span>钱正昊-神秘嘉宾</span>
                  </p>
                </div>
                <div class="play">
                  <a href="#" hover-class="none">
                    <span>></span>
                  </a>
                </div>
              </div>
            </div>
            <div class="hot-music-item">
              <!--名次 -->
              <div class="music-num">01</div>
              <div class="music-content">
                <div class="hot-music-name">
                  <p>神秘嘉宾</p>
                  <p class="singer">
                    <span>@</span>
                    <span>钱正昊-神秘嘉宾</span>
                  </p>
                </div>
                <div class="play">
                  <a href="#" hover-class="none">
                    <span>></span>
                  </a>
                </div>
              </div>
            </div>
            <div class="hot-music-item">
              <!--名次 -->
              <div class="music-num">01</div>
              <div class="music-content">
                <div class="hot-music-name">
                  <p>神秘嘉宾</p>
                  <p class="singer">
                    <span>@</span>
                    <span>钱正昊-神秘嘉宾</span>
                  </p>
                </div>
                <div class="play">
                  <a href="#" hover-class="none">
                    <span>></span>
                  </a>
                </div>
              </div>
            </div>
            <div class="hot-music-item">
              <!--名次 -->
              <div class="music-num">01</div>
              <div class="music-content">
                <div class="hot-music-name">
                  <p>神秘嘉宾</p>
                  <p class="singer">
                    <span>@</span>
                    <span>钱正昊-神秘嘉宾</span>
                  </p>
                </div>
                <div class="play">
                  <a href="#" hover-class="none">
                    <span>></span>
                  </a>
                </div>
              </div>
            </div>
            <div class="hot-music-item">
              <!--名次 -->
              <div class="music-num">01</div>
              <div class="music-content">
                <div class="hot-music-name">
                  <p>神秘嘉宾</p>
                  <p class="singer">
                    <span>@</span>
                    <span>钱正昊-神秘嘉宾</span>
                  </p>
                </div>
                <div class="play">
                  <a href="#" hover-class="none">
                    <span>></span>
                  </a>
                </div>
              </div>
            </div>
            <div class="hot-music-item">
              <!--名次 -->
              <div class="music-num">01</div>
              <div class="music-content">
                <div class="hot-music-name">
                  <p>神秘嘉宾</p>
                  <p class="singer">
                    <span>@</span>
                    <span>钱正昊-神秘嘉宾</span>
                  </p>
                </div>
                <div class="play">
                  <a href="#" hover-class="none">
                    <span>></span>
                  </a>
                </div>
              </div>
            </div>

            <!-- 查看完整榜单 -->
            <div class="look">查看完整榜单 ></div>
          </div>
        </div>
        <!-- 搜索 -->
        <div v-else class="search-box">
          <div class="search">
            <input type="text" placeholder="搜索歌曲 歌手 专辑">
            <icon type="search" size="16"/>
          </div>

          <div class="hot-search">
            <div class="title">热门搜索</div>
            <div class="content">
              <div class="item">防弹少年团</div>
              <div class="item">王嘉尔新歌</div>
              <div class="item">Avicii Forever</div>
              <div class="item">权利的游戏</div>
              <div class="item">神秘的嘉宾</div>
              <div class="item">江山行歌</div>
              <div class="item">路过人间</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import request from "../../utils/request.js";
export default {
  data() {
    return {
      tab: 1,
      // 推荐歌单
      recomMusicList: [],
      newMusic:[],
 
    };
  },
    methods: {
    changTab(index) {
      this.tab = index;
    },
     async getData(){
    let res = await request("https://autumnfish.cn/personalized");
    // console.log(res);
    this.recomMusicList = res.data.result;
     let res1 = await request("https://autumnfish.cn/personalized/newsong");
     console.log(res1);
     this.newMusic=res1.data.result;
     
    }
  },

  mounted() {
    this.getData();

  },


 
};
</script>

<style lang="less">
@import "./index.less";
@import "../../coment/font-ico.css";
</style>
