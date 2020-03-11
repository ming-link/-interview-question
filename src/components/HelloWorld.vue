<template>
  <div class="bg">
    <div class="hello">
      <div class="work">
        <div class="workLeft">
          <div class="head">
            <div class="headImg">
              <img src="../assets/logo.png" alt style="width:100%" />
            </div>
            <div class="headCentre">
              <span class="headFont">Dashboard</span>
              <span class="headFont">Services</span>
              <span class="headFont">History</span>
              <span class="headFont">Actions</span>
            </div>
            <div class="hesdRight">
              <input type="text" class="input" placeholder="search..." />
              <span class="button">
                <img src="../assets/fandajing.png" alt style="width:90%" />
              </span>
            </div>
          </div>
          <div class="split">
            <span class="lowerLeft">Cards</span>
            <span class="lowerRight">View all cards</span>
          </div>
          <div class="nav">
            <div class="card">
              <p class="cardHead">Available balance</p>
              <p class="cardPrice">$ 2,200</p>
              <p class="cardnum">**** **** **** **34</p>
              <p class="cardname">Monzo</p>
              <div>
                <div class="cardun">
                  <div class="carduni carduniLeft"></div>
                  <div class="carduni"></div>
                </div>
              </div>
            </div>
            <div class="card azury">
              <p class="cardHead">Available balance</p>
              <p class="cardPrice">$ 1,300.89</p>
              <p class="cardnum">**** **** **** **67</p>
              <p class="cardname">Monzo</p>
              <div>
                <div class="cardun">
                  <div class="carduni carduniLeft"></div>
                  <div class="carduni"></div>
                </div>
              </div>
            </div>
            <div class="card white">
              <img src="../assets/jia.png" alt class="addCardImg" />
              <p class="newCard">Add New Card</p>
            </div>
          </div>
          <div class="flex">
            <div class="lower">
              <div class="split">
                <span class="lowerLeft">Main Services</span>
                <span class="lowerRight">View all</span>
              </div>
              <div class="flex top">
                <div class="lowerFoot">
                  <table></table>
                  <img src="../assets/weibiaoti8.png" alt class="lowerFootImg" />
                  <p class="lowerFootTitle">Transactions</p>
                </div>
                <div class="lowerFoot">
                  <table></table>
                  <img src="../assets/huaban.png" alt class="lowerFootImg" />
                  <p class="lowerFootTitle">Uttty</p>
                </div>
                <div class="lowerFoot">
                  <table></table>
                  <img src="../assets/tubiaozhizuomoban-.png" alt class="lowerFootImg" />
                  <p class="lowerFootTitle">Loans</p>
                </div>
                <div class="lowerFoot">
                  <table></table>
                  <img src="../assets/weibolu.png" alt class="lowerFootImg" />
                  <p class="lowerFootTitle">Deposits</p>
                </div>
                <div class="lowerFoot">
                  <table></table>
                  <img src="../assets/Concise.png" alt class="lowerFootImg" />
                  <p class="lowerFootTitle">Fast transfer</p>
                </div>
                <div class="lowerFoot">
                  <table></table>
                  <img src="../assets/jiantouarrow491.png" alt class="lowerFootImg" />
                  <p class="lowerFootTitle">Exhange</p>
                </div>
              </div>
            </div>
            <div class="footCenter">
              <div class="split">
                <span class="lowerLeft">Current</span>
                <span class="lowerRight">View all</span>
              </div>
              <div>
                <div class="bottom">
                  <span class="lowerRight">
                    1063873637834
                    <span
                      class="bilateral"
                    >- - - - - - -- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -</span>
                  </span>
                  <span class="lowerLeft">$ 2,200.01</span>
                </div>
                <div class="bottom">
                  <span class="lowerRight">
                    1063873633467
                    <span
                      class="bilateral"
                    >- - - - - - -- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -</span>
                  </span>
                  <span class="lowerLeft">$ 1,300.89</span>
                </div>
                <div class="bottom">
                  <span class="lowerRight">
                    1063873639987
                    <span
                      class="bilateral"
                    >- - - - - - -- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -</span>
                  </span>
                  <span class="lowerLeft">$ 1,848.11</span>
                </div>
              </div>
              <div>
                <div class="split">
                  <span class="lowerLeft">Main Services</span>
                  <span class="lowerRight">View all</span>
                </div>
                <div class="flex">
                  <div id="category" :style="{width: '350px', height: '220px'}"></div>
                  <div class="small">
                    <div class="flex bottom">
                      <span class="lowerRight">Tobal</span>
                      <span class="lowerLeft">$100.09</span>
                    </div>
                    <div class="flex bottom">
                      <span class="lowerRight">Tobal</span>
                      <span class="lowerLeft">$2567.89</span>
                    </div>
                    <div class="flex bottom">
                      <span class="lowerRight">Tobal</span>
                      <span class="lowerLeft">$1848.11</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="aside">
          <Aside />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Aside from "./aside.vue";
export default {
  name: "HelloWorld",
  components: {
    Aside
  },
  data() {
    return {};
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let category = this.$echarts.init(document.getElementById("category"));
      // 绘制图表
      category.setOption({
        xAxis: {
          type: "category",
          data: ["0", "$10", "$20", "$30", "$40", "$50"]
        },
        yAxis: {
          type: "value",
           minInterval: 25
        },
        series: [
          {
            data: [0, 35, 27, 50, 38, 80],
            type: "line",
            smooth: true
          }
        ]
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bg {
  width: 100rem;
  height: 68rem;
  padding: 2rem;
  background: #fdebeb;
  background-image: url('../assets/bg.jpg');
}
.hello {
  position: relative;
  width: 91.25rem;
  height: 60rem;
  margin: 2rem;
  padding-left: 4.375rem;
  padding-top: 2.8125rem;
  border: 1rem solid #fbc3be;
  border-radius: 5rem;
  box-shadow: 0 0 5rem 1rem #fbc3be;
  background: #fdfdfd;
}
.workLeft {
  width: 56.875rem;
}
.head {
  display: flex;
  width: 56.875rem;
  margin-bottom: 4rem;
}
.headImg {
  width: 2.8125rem;
  margin-right: 7.875rem;
}
.headFont {
  font-weight: bold;
  font-size: 1rem;
}
.headCentre {
  width: 24.375rem;
  margin-right: 5.625rem;
  padding-top: 0.625rem;
  display: flex;
  justify-content: space-around;
}
.hesdRight {
  width: 16.875rem;
  margin-left: 2.5rem;
  display: flex;
  justify-content: space-around;
  background: #eee;
  border-radius: 1.2rem;
  height: 30px;
  overflow: hidden;
}

.input {
  border: 0;
  opacity: 0.5;
  background: #eee;
  outline: 0;
  padding: 0.25rem;
  padding-left: 0.625rem;
}
.button {
  width: 2.25rem;
}
.split {
  display: flex;
  justify-content: space-between;
  margin-top: 2rem;
  margin-bottom: 2rem;
}
.nav {
  display: flex;
  margin-bottom: 3rem;
}
.card {
  position: relative;
  width: 19rem;
  height: 8.5rem;
  background: #ff4d56;
  border-radius: 1.2rem;
  padding: 1.3125rem;
  margin-right: 1.2rem;
}
.cardHead {
  font-size: 1rem;
}
.cardPrice {
  margin-top: 0.5rem;
  color: #fff;
  font-size: 1.3rem;
}
.cardnum {
  margin-top: 2rem;
  font-size: 1.4rem;
}
.cardname {
  color: #fff;
  font-size: 1.3rem;
}
.cardun {
  margin: 0;
  position: absolute;
  border-radius: 0.6rem;
  right: 1rem;
  bottom: 1rem;
}
.carduni {
  display: inline-block;
  width: 1.5rem;
  height: 1.5rem;
  background: #ffc24b;
  border-radius: 50%;
}
.carduniLeft {
  background: #e30613;
  margin-right: -0.3125rem;
}
.white {
  background: #eee;
  margin-right: 0;
  text-align: center;
}
.azury {
  background: #0e809a;
}
.addCardImg {
  margin-top: 3.125rem;
  width: 2rem;
}
.newCard {
  margin-top: 0.2rem;
}
.lower {
  width: 16.25rem;
}
.lowerLeft {
  font-size: 0.875rem;
  font-weight: bolder;
}
.lowerRight {
  font-size: 0.625rem;
  color: #999;
}
.flex {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.lowerFoot {
  width: 110px;
  height: 110px;
  border-radius: 1.25rem;
  text-align: center;
  background: #ffffff;
  margin-bottom: 2.5rem;
  box-shadow: 0 0 0.5rem 0.5rem #f6f7f9;
}
.lowerFootImg {
  margin-top: 1.25rem;
  width: 2.5rem;
}
.lowerFootTitle {
  padding: 0.4rem;
  font-size: 0.6rem;
}
.footCenter {
  width: 37.5rem;
}
.bottom {
  margin-bottom: 1.7rem;
}
.bilateral {
  padding-left: 1rem;
  padding-right: 1rem;
}
.small {
  width: 11.25rem;
}
.aside {
  position: absolute;
  top: 0rem;
  right: 0;
}
</style>
