<template>
  <div class="home">
    <div class="top">
      <!-- 导航 -->
      <div class="header">
        <div class="header-logo">
          <div class="logo">
            <span>Rebeccca</span>
          </div>
        </div>
        <div class="header-nav">
          <ul>
            <li v-for="item in headerList" :key="item.id">
              <a
                :class="item.id == headerSelect ? 'active' : ''"
                @click="headerSelected(item.id)"
                >{{ item.name }}</a
              >
            </li>
          </ul>
        </div>
      </div>
      <!-- 轮播 -->
      <div class="carousel">
        <el-carousel
          :interval="3000"
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
            <img
              src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5d4298059889417157e8492750328492.jpg?w=632&h=340"
              alt=""
            />
          </li>
          <li>
            <img
              src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8a43378b96501d7e227a9018fe2668c5.jpg?w=632&h=340"
              alt=""
            />
          </li>
          <li>
            <img
              src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/793913688bfaee26b755a0b0cc8575fd.jpg?w=632&h=340"
              alt=""
            />
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      headerSelect: 0,
      headerList: [
        { id: 0, name: "手表" },
        { id: 1, name: "包包" },
        { id: 2, name: "冬装" },
        { id: 3, name: "夏装" },
        { id: 4, name: "鞋子" },
        { id: 5, name: "皮带" },
        { id: 6, name: "帽子" },
      ],
      bannerHeight: 0,
      bannerImges: [
        {
          id: 0,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/95d9abfb46a60d75885dd74c55523f95.jpg?thumb=1&w=1226&h=460&f=webp&q=90",
        },
        {
          id: 1,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0ef4160c861b998239bce9adb82341e7.jpg?thumb=1&w=1226&h=460&f=webp&q=90",
        },
        {
          id: 2,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5d02e4b6ad0586f61339a042bacb1c45.jpg?w=2452&h=920",
        },
        {
          id: 3,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5d02e4b6ad0586f61339a042bacb1c45.jpg?w=2452&h=920",
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
    headerSelected(index) {
      console.log(index, 999);
      this.headerSelect = index;
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
  .top {
    background: #fff;
    width: 100%;
    .header {
      width: 1226px;
      height: 80px;
      margin: 0 auto;
      background-color: #fff;
      border-radius: 3px;
      .header-logo {
        float: left;
        width: 226px;
        height: 100%;
        .logo {
          width: 100px;
          height: 60px;
          margin: 0 auto;
          position: relative;
          top: 10px;
          color: black;
          font-weight: 600;
          font-size: 24px;
          span {
            position: relative;
            top: 12px;
            font-family: FangSong;
          }
        }
      }
      .header-nav {
        width: calc(100% - 346px);
        height: 100%;
        float: left;
        ul {
          float: left;
          font-size: 16px;
          height: 100%;
          color: #333;
          font-weight: 400;
          li {
            float: left;
            padding-top: 28px;
            a {
              color: #333;
              padding: 31px;
              &:hover {
                color: #ff6700;
                cursor: pointer;
                // background-color: orange;
                // font-weight: 600;
              }
            }
            .active {
              color: #ff6700;
              // background-color: orange;
              // font-weight: 600;
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
      // margin-bottom: 10px;
      border-radius: 3px;
      img {
        width: 1226px;
      }
    }
    .recommend {
      width: 1226px;
      margin: 0 auto;
      background: #fff;
      ul {
        display: flex;
        justify-content: space-between;
        li {
          float: left;
          display: inline-flex;
          margin: 14px 0;
          img {
            height: 170px;
          }
        }
      }
    }
  }
}
</style>
