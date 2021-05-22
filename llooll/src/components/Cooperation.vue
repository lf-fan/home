<template>
  <div>
    <div class="cooperation">
      <h1>合作伙伴</h1>
      <ul>
        <li>
          <h1>GreatWMS官网</h1>
          <a target="_black" href="https://www.56yhz.com">访问官网</a>
          <p>成功和GreatWMS达成合作，成为指定软硬件开发服务商</p>
        </li>
        <li :style="nth2">
          <h1>IOTOS上海</h1>
          <a target="_black" href="https://www.aiotos.net/ ">访问官网</a>
          <p>成功和上海爱投斯达成合作，成为华东地区主要的软硬件开发服务商</p>
        </li>
        <li :style="nth3">
          <h1>嵩景网络 测试平台</h1>
          <a target="_black" href="http://dev.songview.cn/web/#/login"
            >访问官网</a
          >
          <p>测试账户 manager 密码 123456</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  created() {
    setTimeout(() => {
      this.nth3 = "transform:translateX(0px)";
      setTimeout(() => {
        this.nth2 = "transform:translateX(0px)";
      }, 500);
    }, 500);
  },
  data() {
    return {
      nth2: "",
      nth3: "",
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScrollx, true);
  },
  methods: {
    handleScrollx() {
      if (
        window.pageYOffset == 1600 ||
        (window.pageYOffset > 1800 && window.pageYOffset < 2000)
      ) {
        this.nth3 = "transform: translateX(0)";
        this.nth2 = " transform: translateX(0);";
      }
      if (window.pageYOffset < 1500 || window.pageYOffset > 2500) {
        this.nth3 = "transform: translateX(722px)";
        this.nth2 = " transform: translateX(-461px);";
      }
    },
  },
};
</script>

<style  scoped>
ul {
  list-style: none;
}
.cooperation {
  height: 600px;
  /* height: 100%; */
  width: 1500px;
  margin: 0 auto;
  /* margin-top: 1293px; */
  margin-top: 1152px;
  background-image: url(../assets/page3.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  position: absolute;
  left: 0;
  width: 100%;
}
.cooperation > h1 {
  text-align: center;
  /* color: #fff; */
   color: yellowgreen;
  font-size: 50px;
}
.cooperation ul {
  width: 100%;
}
.cooperation ul li {
  /* margin: 0px 5%; */
  width: 400px;
  height: 400px;
  border: 3px solid;
  border-radius: 10px;
  border-color: #ccc;
  float: left;
  margin-left: 55px;
  text-align: center;
  position: relative;
  left: 0;
  transition: all 1s ease;
}
.cooperation ul li:nth-child(2) {
  transform: translateX(-461px);
}
.cooperation ul li:nth-child(3) {
  transform: translateX(722px);
}
.cooperation ul li h1 {
  padding: 10% 0;
  /* color: #ccc; */
     color: yellowgreen;
}
.cooperation ul li p {
  padding-top: 50px;
  /* color: #ccc; */
  color: yellowgreen;
}
.cooperation ul li a {
  text-decoration: none;
  font-size: 20px;
  transition: all 0.8s ease;
  font-weight: bold;
}
.cooperation ul li a:hover {
  color: #ccc;
}
</style>