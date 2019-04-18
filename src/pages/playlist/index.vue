<template>
  <div>
    <!-- 头部区域 -->
    <div class="header">
      <div class="song-list">
        <!-- 歌单图片 -->
        <div class="left">
          <div class="icon">歌单</div>
          <img src alt>
        </div>
        <!-- 歌单信息 -->
        <div class="right">
          <!-- 歌单名 -->
          <div class="song-name">
            <p>用一首歌,讲珍惜眼前人的故事</p>
          </div>
          <!-- 创建者 -->
          <div class="song-creator">
            <div class="creator-head">
              <img src alt>
            </div>
            <span class="creator-name">虎锐</span>
          </div>
        </div>
      </div>

      <div class="song-describe">
        <!-- 标签 -->
        <div class="song-label">
          标签:
          <span>话语</span>
          <span>话语</span>
          <span>话语</span>
        </div>
        <!-- 歌单简介 -->
        <div
          class="abstract"
        >简介：三十岁了。在屏幕上郑重的打下这几个字时，难免心生感伤，应该属于春怨范畴。傍晚宣哥说他从莲藕省驱车疾驰900多公里回到慈溪，我问他，回老本行重新搞起运输了吗。他说不是，仅仅是送家姐去趟孝感办事。莫名怀念起过去啊，和他相谈甚欢，和他通宵的聊最好来点酒微醺迷醉并喟叹知己难求。过了最好的年龄，夜谈，展望，寒暄，开始隐没在好友圈中。他浒山镇的玉米长势喜人，乡间小路走到头就有广袤无垠的海，海岸有些小灌木。</div>
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
      <div class="music-list">
        <div class="item">
          <div class="left">1</div>
          <div class="right">
            <div class="music-content">
              <p class="music-name">想起</p>
              <p class="music-singer">江美琪-想起</p>
            </div>

            <div class="play">
              <span class="iconfont icon-bofang"></span>
            </div>
          </div>
        </div>
        <div class="item">
          <div class="left">1</div>
          <div class="right">
            <div class="music-content">
              <p class="music-name">想起</p>
              <p class="music-singer">江美琪-想起</p>
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

      <div class="splendid">
        <div class="top">
          <div class="comment-meta">
            <img src alt>
            <div class="comment-uset">
              <p class="nickname">壁纸酱neysa_</p>
              <p class="time">10:12</p>
            </div>
          </div>

          <!-- 点赞 -->
          <div class="like">
            <span class="num">95</span>
            <span class="iconfont icon-dianzan"></span>
          </div>
        </div>
        <div class="bottom">
          <span class="text">
            ✔真诚建议如果两个人之间如果有不快乐的事情，见个面坦诚地去聊一聊吧。
            我觉得见面沟通太重要了，
            对着手机屏幕什么狠话都说得出。
            见面就不一样了，见面会心软，会看见泪光，会得到拥抱。
            相视而笑的时候在想，有什么好争吵的呢，不如珍惜当下好好抱一抱。
          </span>
        </div>
      </div>

      <div class="title">
        最新评论
        <span>(85)</span>
      </div>
      <div class="splendid">
        <div class="top">
          <div class="comment-meta">
            <img src alt>
            <div class="comment-uset">
              <p class="nickname">壁纸酱neysa_</p>
              <p class="time">10:12</p>
            </div>
          </div>

          <!-- 点赞 -->
          <div class="like">
            <span class="num">95</span>
            <span class="iconfont icon-dianzan"></span>
          </div>
        </div>
        <div class="bottom">
          <span class="text">✔真诚建议如果两个人之间如果有不快乐的事。</span>
        </div>
      </div>

      <!-- 查看全部 -->
      <div class="look-all">查看全部85条评论 <span class="iconfont icon-right"></span></div>

      <!-- 收藏歌单 -->
      <div class="collect-song">
        <button><span class="icon icon-bofang"></span> 收藏歌单</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="less">
@import "./index.less";
@import "../../coment/font-ico.css";
</style>
