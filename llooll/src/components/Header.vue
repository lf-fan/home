<template>
  <div class="box">
    <div class="header-top clearfix">
      <div class="left">
        <ul>
          <li>
            <img
              src="../assets/logo.jpg"
              title="嵩哥网络科技"
              alt="无法加载图片"
            />
          </li>
        </ul>
      </div>
      <div class="right">
        <ul>
          <li @click="home">首页</li>
          <li @click="case_home">案例</li>
          <li @click="cooperation">合作</li>
          <li>价格</li>
          <li>关于</li>
          <li>介绍</li>
          <li>联系我们</li>
        </ul>
      </div>
    </div>
    <!-- 第一页 -->
    <div class="home">
      <div class="video">
        <video
          autoplay="autoplay"
          muted="muted"
          loop="loop"
          src="../assets/video/logo.mp4"
        ></video>
      </div>
      <div class="words" :class="words">
        <div class="fonts" :style="move">
          <p>数字创意,预见未来</p>
          <p>Digital creativity meet the future</p>
          <p>为您打造全新互联网品牌形象</p>
        </div>
      </div>
    </div>
    <!-- 第二页 -->
    <div id="case" ref="pronbit" class="case">
      <h1>案例</h1>
      <ul>
        <li :style="case_moves"><img src="../assets/albb.jpg" alt="" /></li>
        <li :style="case_moves"><img src="../assets/durex.jpg" alt="" /></li>
        <li :style="case_moves">
          <img src="../assets/microsoft.jpg" alt="" />
        </li>
        <li :style="case_moves"><img src="../assets/oppo.jpg" alt="" /></li>
        <li :style="case_moves"><img src="../assets/wangyi.jpg" alt="" /></li>
        <li :style="case_moves"><img src="../assets/Google.jpg" alt="" /></li>
        <li :style="case_moves"><img src="../assets/huawei.jpg" alt="" /></li>
        <li :style="case_moves"><img src="../assets/apple.jpg" alt="" /></li>
      </ul>
    </div>
    <div class="page3"></div>
  </div>
</template>

<script>
export default {
  created() {
    setTimeout(() => {
      this.move = "transform:translateY(50px)";
    }, 1000);
  },
  mounted() {
    window.addEventListener("scroll", this.handleScrollx, true);
  },
  methods: {
    handleScrollx() {
      console.log("滚动高度", window.pageYOffset);
      // console.log(
      //   "距离顶部高度",
      //   this.$refs.pronbit.getBoundingClientRect().top
      // );
      if (
        window.pageYOffset == 1100 ||
        (window.pageYOffset > 1200 && window.pageYOffset < 1300)
      ) {
        // alert('ok')
        this.case_moves = "transform:translateY(0)";
      }
      if (window.pageYOffset < 1100 || window.pageYOffset > 1800) {
        // setTimeout(() => {
        this.case_moves = "transform:translateY(600px)";
        // }, 2000);
      }
    },
    case_home() {
      document.documentElement.scrollTop = 1100;
    },
    cooperation() {
      document.documentElement.scrollTop = 1920;
    },
    home() {
      document.documentElement.scrollTop = 0;
    },
  },
  data() {
    return {
      move: "",
      words: "",
      case_moves: "",
    };
  },
};
</script>

<style scoped>
.clearfix::after {
  content: "";
  display: block;
  clear: both;
  min-width: 1200px;
}
ul {
  width: 100%;
  height: 100%;
  list-style: none;
}

.header-top {
  height: 50px;
  /* border-bottom: solid; */
  /* border-color: rgb(161, 144, 144); */
}
.header-top > .left {
  float: left;
}
.header-top > .right {
  float: right;
}

.header-top > .left ul > li > img {
  cursor: pointer;
  width: 150px;
  margin-top: -16px;
  height: 50px;
}

.header-top .right ul li {
  cursor: pointer;
  float: left;
  margin-left: 15px;
  transition: all 0.5s ease;
  font-weight: bold;
  color: #fff;
  padding-right: 30px;
}
.header-top .right ul li:hover {
  color: rgb(90, 168, 221);
}

video {
  position: absolute;
  right: 0;
  top: 0;
  bottom: 50%;
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  z-index: -999;
}

.words {
  width: 1200px;
  height: 500px;
  /* border: 5px solid; */
  color: #fff;
  font-size: 50px;
  text-align: center;
  margin: 5% auto;
  border-radius: 10px;
  overflow: hidden;
}
.words .fonts {
  position: relative;
  transform: translateY(460px);
  transition: all ease 1s;
}
.case {
  background-image: url(../assets/s_banner.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  /* border: 5px solid; */
  height: 780px;
  width: 100%;
  overflow: hidden;
  margin: 0 auto;
  margin-top: 372px;
  position: absolute;
  right: 0;
}
.case h1 {
  color: #ccc;
  font-size: 50px;
  text-align: center;
}
.case ul li img {
  cursor: pointer;
  width: 100%;
  height: 100%;
  transition: all 1s ease;
  position: relative;
}
.case ul {
  width: 1500px;
  height: 500px;
  margin: 0 auto;
  box-sizing: border-box;
}
.case ul li {
  float: left;
  width: 300px;
  height: 200px;
  margin: 50px 30px;
  border-radius: 10px;
  /* position: relative; */
  transition: all 1s ease;
  transform: translateY(600px);
}
.case ul li img:hover {
  width: 310px;
  height: 210px;
  transform: rotate(360deg);
}
/* .page3{
  margin-top: 800px;
  height: 1200px;
  border: 1px solid;
} */
</style>
