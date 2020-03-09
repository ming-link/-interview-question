<template>
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
            <input type="text" class="input" />
            <span class="button">
              <img src="../assets/fandajing.png" alt style="width:90%" />
            </span>
          </div>
        </div>
        <div class="split">
          <span>Cards</span>
          <span>View all cards</span>
        </div>
        <div style="display: flex;">
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
            <div class="flex">
              <div class="lowerFoot">
                <table></table>
                <img src="../assets/weibiaoti8.png" alt class="lowerFootImg" />
                <p class="lowerFootTitle">Transactions</p>
              </div>
              <div class="lowerFoot">
                <table></table>
                <img src="../assets/huaban.png" alt class="lowerFootImg" />
                <p class="lowerFootTitle">Transactions</p>
              </div>
              <div class="lowerFoot">
                <table></table>
                <img src="../assets/tubiaozhizuomoban-.png" alt class="lowerFootImg" />
                <p class="lowerFootTitle">Transactions</p>
              </div>
              <div class="lowerFoot">
                <table></table>
                <img src="../assets/weibolu.png" alt class="lowerFootImg" />
                <p class="lowerFootTitle">Transactions</p>
              </div>
              <div class="lowerFoot">
                <table></table>
                <img src="../assets/Concise.png" alt class="lowerFootImg" />
                <p class="lowerFootTitle">Transactions</p>
              </div>
              <div class="lowerFoot">
                <table></table>
                <img src="../assets/jiantouarrow491.png" alt class="lowerFootImg" />
                <p class="lowerFootTitle">Transactions</p>
              </div>
            </div>
          </div>
          <div>
            <div class="split">
              <span>Current</span>
              <span>View all</span>
            </div>
            <div>
              <span>
                1063873637834
                <span>----------------------------------------------------</span>
              </span>
              <span>$2,200.01</span>
            </div>
            <div>
              <span>
                1063873637834
                <span>----------------------------------------------------</span>
              </span>
              <span>$2,200.01</span>
            </div>
            <div>
              <span>
                1063873637834
                <span>----------------------------------------------------</span>
              </span>
              <span>$2,200.01</span>
            </div>
            <div>
              <div class="split">
                <span class="lowerLeft">Main Services</span>
                <span class="lowerRight">View all</span>
              </div>
              <div>
                <div id="category" :style="{width: '250px', height: '150px'}"></div>
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
      let myChart = this.$echarts.init(document.getElementById("category"));
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  position: relative;
  width: 57.5rem;
  padding-left: 1.875rem;
  padding-top: 1.25rem;
  margin: o auto;
  border: 0.25rem solid rgb(0, 145, 170);
  border-radius: 2.3rem;
}
.workLeft {
  width: 40.875rem;
}
.head {
  display: flex;
}
.headImg {
  width: 2rem;
}
.headFont {
  font-weight: bold;
  font-size: 0.875rem;
}
.headCentre {
  margin-left: 3rem;
  margin-right: 0.6rem;
  width: 20rem;
  padding-top: 0.625rem;
  display: flex;
  justify-content: space-around;
}
.hesdRight {
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
  padding-top: 0.08rem;
  width: 2.25rem;
}
.split {
  display: flex;
  justify-content: space-between;
  margin-top: 1.875rem;
  margin-bottom: 0.9375rem;
}
.card {
  position: relative;
  width: 11.25rem;
  height: 6.25rem;
  background: pink;
  border-radius: 0.625rem;
  padding: 0.3125rem;
  padding-left: 0.9375rem;
  margin-right: 1.2rem;
}
.cardHead {
  font-size: 0.5rem;
}
.cardPrice {
  margin-top: -0.5rem;
  color: #fff;
}
.cardname {
  margin-top: -1rem;
}
.cardun {
  margin: 0;
  width: 2.5rem;
  height: 1.5rem;
  position: absolute;
  border-radius: 0.6rem;
  top: 4.375rem;
  right: 0.5rem;
}
.carduni {
  display: inline-block;
  width: 1.25rem;
  height: 1.5rem;
  background: #ff0;
  border-radius: 50%;
}
.carduniLeft {
  background: red;
  margin-right: -0.3125rem;
}
.white {
  background: #eee;
}
.azury {
  background: royalblue;
}
.addCardImg {
  display: block;
  margin-top: 2rem;
  margin-left: 4.5rem;
  width: 2rem;
}
.newCard {
  padding-left: 2.2rem;
  margin-top: 0.2rem;
}
.lower {
  width: 10.7rem;
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
  width: 5.0625rem;
  height: 5.0625rem;
  background: seashell;
  border-radius: 0.7rem;
  margin-bottom: 0.5rem;
}

.lowerFootImg {
  display: block;
  margin-top: 0.6rem;
  margin-left: 1.2rem;
  width: 2.5rem;
}
.lowerFootTitle {
  padding: 0.4rem;
  margin-top: 0.15rem;
  font-size: 0.6rem;
}
.aside {
  position: absolute;
  top: 0;
  right: 0;
}
</style>
