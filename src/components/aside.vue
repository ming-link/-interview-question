<template>
  <div class="homeRight">
    <div class="news">
      <div>
        <img src="../assets/lingdang.png" alt class="newsImg" />
        <span></span>
      </div>
      <div>
        <b class="userName">Anastasia</b>
        <img src="../assets/touxiang.jpeg" alt class="newst" />
      </div>
    </div>
    <div class="pie">
      <div id="pie" :style="{width: '150px', height: '150px'}"></div>
      <div class="pieCentre">
        <b style="font-size:1.2rem">$5,349</b>
        <br />
        <span style="font-size:0.6rem;padding-left:0.4rem">Balance</span>
      </div>
    </div>
    <div class="list">
      <div class="news">
        <b class="listTopFont">Transactions</b>
        <b class="listTopFont">
          Today
          <img src="../assets/xiajiangtou.png" alt class="listTopImg" />
        </b>
      </div>
      <div>
        <div class="news top">
          <img src="../assets/qiu.png" alt class="listImg" />
          <b class="brief">Dribbble Pro Plan</b>
          <b class="brief money">- $100</b>
        </div>
        <div class="news top">
          <img src="../assets/san (2).png" alt class="listImg" />
          <b class="brief">Dribbble Pro Plan</b>
          <b class="brief money">- $100</b>
        </div>
        <div class="news top">
          <img src="../assets/san (1).png" alt class="listImg" />
          <b class="brief">Dribbble Pro Plan</b>
          <b class="brief money">- $100</b>
        </div>
      </div>
      <div class="foot">
        <button class="button">
          <span class="buttonIn">Rransfer Money</span>
          <img src="../assets/jiantou.png" alt class="buttonImg" />
        </button>
        <img src alt />
      </div>
    </div>
  </div>
</template>

<script>
let echarts = require("echarts/lib/echarts");
// 引入柱状图组件
require("echarts/lib/chart/bar");
// 引入提示框和title组件
require("echarts/lib/component/tooltip");
require("echarts/lib/component/title");
export default {
  data() {
    return {};
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let pie = this.$echarts.init(document.getElementById("pie"));
      // 绘制图表
      pie.setOption({
        tooltip: {
          trigger: "item"
        },
        legend: {
          orient: "vertical"
        },
        series: [
          {
            name: "访问来源",
            type: "pie",
            radius: ["75%", "100%"],
            avoidLabelOverlap: false,
            label: {
              normal: {
                show: false,
                position: "center"
              },
              emphasis: {
                show: true,
                textStyle: {
                  fontSize: "30",
                  fontWeight: "bold"
                }
              }
            },
            labelLine: {
              normal: {
                show: false
              }
            },
            data: [{ value: 1 }, { value: 1 }, { value: 1 }, { value: 1 }]
          }
        ]
      });
    }
  }
};
</script>

<style scoped>
.homeRight {
  width: 13.75rem;
  height: 33.2rem;
  border-radius: 2rem;
  background: white;
  padding: 0.625rem;
}
.news {
  display: flex;
  justify-content: space-between;
}
.newsImg {
  width: 1.875rem;
}
.newst {
  width: 2.5rem;
  border-radius: 50%;
  vertical-align: middle;
}
.userName {
  display: inline-block;
  font-size: 0.75rem;
}
.pie {
  margin-top: 1rem;
  margin-bottom: 1rem;
  padding-left: 2.1875rem;
  position: relative;
}
.pieCentre {
  width: 60px;
  position: absolute;
  top: 3.75rem;
  left: 5.3rem;
}
.top {
  margin-top: 0.9375rem;
}
.list {
  padding: 0.5rem;
}
.listTopFont {
  font-size: 0.75rem;
  color: #aaa;
}
.listTopImg {
  width: 0.5rem;
}
.listImg {
  width: 1.5rem;
}
.brief {
  display: inline-block;
  padding-top: 0.2rem;
  font-size: 0.75rem;
}
.foot {
  margin-top: 1.875rem;
  position: relative;
}
.button {
  width: 100%;
  background: #d6204b;
  padding-left: 1rem;
  padding-right: 0.8rem;
  border-radius: 0.9375rem;
  border: 0;
  outline: 0;
  display: flex;
  justify-content: space-between;
}
.buttonIn {
  display: inline-block;
  margin-top: 0.3125rem;
}
.buttonImg {
  width: 1.8rem;
  vertical-align: middle;
}
</style>