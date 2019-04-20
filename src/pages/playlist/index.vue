<template>
  <div>
    <!-- 头部区域 -->
    <div class="header" >
      <!-- <img class="bgc-img" :src="playList.coverImgUrl"  alt=""> -->
      <div class="song-list">
        <!-- 歌单图片 -->
        <div class="left">
          <div class="icon">歌单</div>
          <img :src="playList.coverImgUrl" alt>
        </div>
        <!-- 歌单信息 -->
        <div class="right">
          <!-- 歌单名 -->
          <div class="song-name">
            <p>{{playList.name}}</p>
          </div>
          <!-- 创建者 -->
          <div class="song-creator">
            <div class="creator-head">
              <img :src="playList.creator.avatarUrl" alt>
            </div>
            <span class="creator-name">{{playList.creator.nickname}}</span>
          </div>
        </div>
      </div>

      <div class="song-describe">
        <!-- 标签 -->
        <div class="song-label">
          标签:
          <span v-for="(item,index) in playList.tags" :key="index">{{item}}</span>
        </div>
        <!-- 歌单简介 -->
        <div class="abstract">{{playList.description}}</div>
        <!-- 等多内容 -->
        <div class="song-more">
          <span class="iconfont icon-xiajiantou"></span>
        </div>
      </div>
    </div>

    <!-- 歌曲区域 -->
    <div class="cont">
      <div class="title">歌曲列表</div>

      <!-- 歌曲 -->
      <div class="music-list" v-for="(item,index) in playList.tracks" :key="index">
        <div class="item">
          <div class="left">{{index+1}}</div>
          <div class="right">
            <div class="music-content">
              <p class="music-name">{{item.name}}</p>
              <p class="music-singer">{{item.ar[0].name}}-{{item.al.name}}</p>
            </div>

            <div class="play">
              <span class="iconfont icon-bofang"></span>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- 评论区域 -->
    <div class="bottom">
      <div class="title">精彩评论</div>

      <div class="splendid" v-for="(item,index) in hotComments" :key="index">
        <div class="top">
          <div class="comment-meta">
            <img :src="item.user.avatarUrl" alt>
            <div class="comment-uset">
              <p class="nickname">{{item.user.nickname}}</p>
              <p class="time">{{item.time}}</p>
            </div>
          </div>

          <!-- 点赞 -->
          <div class="like">
            <span class="num">{{item.likedCount}}</span>
            <span class="iconfont icon-dianzan"></span>
          </div>
        </div>
        <div class="bottom">
          <span class="text">
            <span v-if="item.beReplied.length>0">回复<span class="text-at">@{{item.beReplied[0].user.nickname}}: </span></span>
          {{item.content}}
          <div v-if="item.beReplied.length>0">
            @{{item.beReplied[0].user.nickname}}: {{item.beReplied[0].content}}
          </div>
          </span>
        </div>
      </div>

      <div class="title">
        最新评论
        <span>({{comments.length}})</span>
      </div>
      <div class="splendid" v-for="(item,index) in comments" :key="index">
        <div class="top">
          <div class="comment-meta">
            <img :src="item.user.avatarUrl" alt>
            <div class="comment-uset">
              <p class="nickname">{{item.user.nickname}}</p>
              <p class="time">{{item.time}}</p>
            </div>
          </div>

          <!-- 点赞 -->
          <div class="like">
            <span class="num" v-if="item.likedCount!=0">{{item.likedCount}}</span>
            <span class="iconfont icon-dianzan"></span>
          </div>
        </div>
        <div class="bottom">
          <span class="text">
            <span v-if="item.beReplied.length>0">回复<span class="text-at">@{{item.beReplied[0].user.nickname}}: </span></span>
          {{item.content}}
          <div v-if="item.beReplied.length>0">
            @{{item.beReplied[0].user.nickname}}: {{item.beReplied[0].content}}
          </div>
          </span>
        </div>
      </div>

      <!-- 查看全部 -->
      <a href="/pages/applink/main" class="look-all">
        查看全部{{total}}条评论
        <span class="iconfont icon-right"></span>
      </a>

      <!-- 收藏歌单 -->
      <div class="collect-song">
        <button>
          <span class="icon icon-bofang"></span> 收藏歌单
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import request from "../../utils/request.js";
export default {
  data() {
    return {
        //  获取歌单歌曲列表
      playList: [],
      // 热门评论
      hotComments:[],
      // 最新评论
      comments:[],
      // 全部评论
      total:[]
    };
  },
  methods: {},
  async mounted() {
    //  获取歌单歌曲列表
    //歌单id
    var id = this.$root.$mp.query.id;
    let res = await request("https://autumnfish.cn/playlist/detail?id=" + id);
    this.playList = res.data.playlist;
    //歌单评论
    let res1= await request("https://autumnfish.cn/comment/playlist?id="+id)
    console.log(res1);
    this.hotComments=res1.data.hotComments;
    this.comments=res1.data.comments;
    this.total=res1.data.total;
    console.log(this.comments);
    
    
    
  }
};
</script>

<style scoped lang="less">
@import "./index.less";
@import "../../coment/font-ico.css";
</style>
