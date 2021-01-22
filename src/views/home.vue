<template>
  <div class="home">
    <!-- 导航 -->
    <div class="header">
      <div class="header-logo">
        <div class="logo">
          <span>rebeccca</span>
        </div>
      </div>
      <div class="header-nav">
        <ul>
          <li>
            <a href="">手表</a>
          </li>
          <li>
            <a href="">包包</a>
          </li>
          <li>
            <a href="">冬装</a>
          </li>
          <li>
            <a href="">夏装</a>
          </li>
          <li>
            <a href="">鞋子</a>
          </li>
          <li>
            <a href="">皮带</a>
          </li>
          <li>
            <a href="">帽子</a>
          </li>
        </ul>
      </div>
    </div>
    <!-- 轮播 -->
    <div class="carousel">
      <el-carousel
        :interval="3000"
        type="card"
        arrow="always"
        :height="bannerHeight + 'px'"
      >
        <el-carousel-item v-for="item in bannerImges" :key="item.id">
          <img ref="bannerHeight" :src="item.img" alt="" @load="bannerLoad" />
        </el-carousel-item>
      </el-carousel>
    </div>
    <!-- 官方推荐 -->
    <div class="recommend">
      <ul>
        <li>
          <img src="../assets/img/1.jpeg" alt="" />
        </li>
        <li>
          <img src="../assets/img/1.jpeg" alt="" />
        </li>
        <li>
          <img src="../assets/img/1.jpeg" alt="" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      bannerHeight: 0,
      bannerImges: [
        {
          id: 0,
          img: require("../assets/img/1.jpeg"),
        },
        {
          id: 1,
          img: require("../assets/img/2.jpeg"),
        },
        {
          id: 2,
          img: require("../assets/img/3.jpeg"),
        },
      ],
    };
  },
  mounted() {
    this.bannerLoad();
    window.addEventListener(
      "resize",
      () => {
        this.bannerHeight = this.$refs.bannerHeight[0].height;
        this.bannerLoad();
      },
      false
    );
  },
  methods: {
    //   banner高度自适应图片高度
    bannerLoad() {
      this.$nextTick(() => {
        this.bannerHeight = this.$refs.bannerHeight[0].height;
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  font: 14px/1.5 Helvetica Neue, Helvetica, Arial, Microsoft Yahei,
    Hiragino Sans GB, Heiti SC, WenQuanYi Micro Hei, sans-serif;
  color: #333;
  background-color: #ededed;
  min-width: 1226px;
  height: 1500px;
  .header {
    width: 1226px;
    height: 100px;
    margin: 0 auto;
    background-color: #fff;
    margin-bottom: 20px;
    // border-radius: 3px;
    // box-shadow: 1px 1px 3px #fff;
    .header-logo {
      float: left;
      width: 226px;
      height: 100%;
      //   margin: 10px 80px 10px 40px;
      .logo {
        width: 100px;
        height: 60px;
        margin: 15px 0 15px 46px;
        padding: 5px;
        color: #fff;
        font-weight: 600;
        font-size: 20px;
        background-color: orange;
        border-radius: 5px;
        box-shadow: 1px 1px 3px orange;
        span {
          position: relative;
          top: 12px;
          font-family: FangSong;
        }
      }
    }
    .header-nav {
      width: calc(100% - 346px);
      height: 100px;

      float: left;
      //   float: left;
      ul {
        float: left;
        font-size: 16px;
        height: 100%;
        //   margin: 20px;
        // vertical-align: middle;

        li {
          float: left;
          margin-top: 38px;
          a {
            color: #333;
            padding: 40px;
            &:hover {
              color: #fff;
              background-color: orange;
              font-weight: 600;
            }
          }
        }
      }
    }
  }
  .carousel {
    width: 1226px;
    clear: both;
    margin: 0 auto;
    background: #fff;
    margin-bottom: 20px;
    img {
      height: 450px;
    }
  }
  .recommend {
    width: 1226px;
    height: 250px;
    margin: 0 auto;
    background: #fff;
    ul {
      margin: 0 auto;
      text-align: center;
      li {
        float: left;
        margin: 25px 54px;
        img {
          height: 200px;
        }
      }
    }
  }
}
</style>
