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
    <div class="main">
      <div class="one">
        <p class="item">
          <span class="type">手表</span>
          <a>
            <span class="more"
              >查看更多
              <span class="arrorRight">>></span>
            </span>
          </a>
        </p>
        <ul>
          <li v-for="item in productOne" :key="item.id">
            <a>
              <img :src="item.img" alt="" />
              <p class="title">{{ item.title }}</p>
              <p class="content">
                {{ item.content }}
              </p>
              <p class="price">{{ item.price }}</p>
            </a>
          </li>
        </ul>
        <ul>
          <li v-for="item in productOne" :key="item.id">
            <a>
              <img :src="item.img" alt="" />
              <p class="title">{{ item.title }}</p>
              <p class="content">
                {{ item.content }}
              </p>
              <p class="price">{{ item.price }}</p>
            </a>
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
      productOne: [
        {
          id: 1,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 2,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 3,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 4,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 5,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
      ],
      productTwo: [
        {
          id: 1,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 2,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 3,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 4,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
        },
        {
          id: 5,
          img:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/5a260090e0e08770b0bd865845a4b4ab.jpg",
          title: "小米11",
          content: "2k888,四曲面屏",
          price: "￥5999",
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
  .main {
    width: 100%;
    background: #ededed;
    .one {
      width: 1226px;
      margin: 0 auto;
      // border: 1px solid red;
      .item {
        margin: 0;
        font-size: 22px;
        font-weight: 200;
        line-height: 58px;
        color: #333;
        text-align: left;
        margin-bottom: -10px;
        display: flex;
        justify-content: space-between;
        .type {
          text-align: left;
        }
        .more {
          text-align: right;
          font-size: 14px;
        }
        .arrorRight {
          padding: 4px;
          border-radius: 16px;
          font-size: 12px;
          line-height: 12px;
          vertical-align: 1px;
          -webkit-transition: all 0.4s;
          transition: all 0.4s;
          font-weight: 500;
        }
      }
      ul {
        display: flex;
        justify-content: space-between;
        margin: 10px 0;
        li {
          float: left;
          width: 234px;
          background: #fff;
          a {
            img {
              width: 160px;
              margin-top: 15px;
            }
            h4 {
              margin: 15px;
            }
            p {
              margin: 15px;
              font-size: 12px;
            }
            .title {
              color: #333;
              font-size: 14px;
              font-weight: 500;
            }
            .content {
              color: #b0b0b0;
            }
            .price {
              color: #ff6700;
              font-size: 16px;
              font-weight: 500;
            }
          }
        }
      }
    }
  }
}
</style>
