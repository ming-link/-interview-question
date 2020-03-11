<template>
  <div class="homeRight">
    <div class="news">
      <div class="hint">
        <img src="../assets/lingdang.png" alt class="newsImg" />
        <div class="dot"></div>
      </div>
      <div>
        <b class="userName">Anastasia</b>
        <img src="../assets/touxiang.jpeg" alt class="newst" />
      </div>
    </div>
    <div class="p">
      <div id="p" :style="{width: '222px', height: '222px'}"></div>
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
          <div class="itemFont">
            <b class="brief">Dribbble Pro Plan</b>
            <b class="brief money">- $100</b>
          </div>
        </div>
        <div class="news top">
          <img src="../assets/san (2).png" alt class="listImg" />
          <div class="itemFont">
            <b class="brief">Dribbble Pro Plan</b>
            <b class="brief money addMoney">- $230</b>
          </div>
        </div>
        <div class="news top">
          <img src="../assets/san (1).png" alt class="listImg" />
          <div class="itemFont">
            <b class="brief">Dribbble Pro Plan</b>
            <b class="brief money">- $3000</b>
          </div>
        </div>
      </div>
      <div class="foot">
        <button class="button">
          <span class="buttonIn">Transfer Money</span>
          <img src="../assets/jiantou.png" alt class="buttonImg" />
        </button>
        <img src="../assets/communicate.png" alt class="footXi" />
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
      let p = this.$echarts.init(document.getElementById("p"));
      // 绘制图表
      p.setOption({
         title: { text: '$5,349',subtext:'Balance',left:'center',top:'center',textStyle:{fontStyle:'normal', fontSize:22},subtextStyle:{top:'y:10'} },
         tooltip: {
          trigger: "item"
        },
        legend: {
          orient: "vertical"
        },
        color:['white','#212f46','#0e809a','#ff2934',],
        series: [
          {
            name: "",
            type: "pie",
            radius: ["65%", "85%"],
            avoidLabelOverlap: true,
             roundCap:true,
            label: {
              normal: {
                show: true,
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
  width: 23.75rem;
  height: 58.75rem;
  border-radius: 5rem;
  background: white;
  padding: 2rem;
  box-shadow: -0.3125rem 0 1rem -0.2rem #f6f7f9;
}
.news {
  display: flex;
  justify-content: space-between;
}
.hint {
  position: relative;
}
.dot {
  position: absolute;
  width: 0.5rem;
  height: 0.5rem;
  background: red;
  border-radius: 50%;
  top: .4rem;
  right: .4rem;
}
.itemFont {
  width: 15rem;
  line-height: 3.75rem;
  display: flex;
  justify-content: space-between;
}
.newsImg {
  width: 2.2rem;
}
.newst {
  width: 3rem;
  border-radius: 50%;
  vertical-align: middle;
}
.userName {
  display: inline-block;
  font-size: 1rem;
  padding-right: 0.525rem;
}
.p {
  width: 23.75rem;
  margin-top: 4rem;
  margin-bottom: 1.5rem;
  text-align: center;
  padding-left: 5rem;
  position: relative;
}
.pieCentre {
  width: 60px;
  position: absolute;
  top: 3.75rem;
  left: 5.3rem;
}
.top {
  margin-top: 1.5rem;
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
  width: 3.75rem;
  background: white;
}
.brief {
  display: inline-block;
  padding-top: 0.2rem;
  font-size: 0.75rem;
}
.money {
  color: red;
}
.addMoney {
  color: #0e809a;
}
.foot {
  margin-top: 4rem;
  position: relative;
}
.button {
  display: block;
  width: 100%;
  height: 3.125rem;
  background: #ff4d56;
  padding-left: 1.5rem;
  padding-right: 1.5rem;
  border-radius: 2rem;
  border: 0;
  outline: 0;
  display: flex;
  justify-content: space-between;
}
.buttonIn {
  display: inline-block;
  margin-top: 0.7rem;
  color: azure;
}
.buttonImg {
  width: 2.5rem;
  vertical-align: middle;
}
.footXi {
  display: block;
  width: 2.5rem;
  position: absolute;
  border-radius: 50%;
  right: 0;
  top: 9rem;
}
</style>