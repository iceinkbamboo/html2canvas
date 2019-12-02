<template>
  <div class="box">
    <div style="margin-top: 400px;"></div>

    <div class="box1">
      <p>
        段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段
      </p>
    </div>
    <div class="home" ref="toimg">
      <p>
        段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1段落1
      </p>
      <p>段2</p>
      <p>段3</p>
      <p>段落4</p>
      <p>段落5</p>
      <p>段落6</p>
      <p>段落7段落一</p>
      <p>段落8</p>
      <p>段落9</p>
      <p>段落10</p>
      <p>段落11</p>
      <p>段落12</p>
      <p>段落13</p>
      <p>段落14</p>
    </div>
    <div class="btn" @click="toImage">生成图片</div>
  </div>
</template>

<script>
import html2canvas from "html2canvas";
export default {
  name: "home",
  components: {},
  data() {
    return {};
  },
  methods: {
    toImage() {
      let dom = this.$refs.toimg;
      html2canvas(dom, {
        width: dom.offsetWidth,
        height: dom.offsetHeight,
        y: dom.offsetTop
      }).then(canvas => {
        dom.append(canvas);
        let link = document.createElement("a");
        link.href = canvas.toDataURL();
        link.setAttribute("download", "canvas.png");
        link.style.display = "none";
        document.body.appendChild(link);
        link.click();
      });
    }
  }
};
</script>

<style lang="less" scoped>
.box {
  height: 2000px;
}
.box1 {
  width: 200px;
  height: 400px;
  background: red;
  margin: 0 auto;
}
.home {
  width: 400px;
  height: 400px;
  background: #ff6600;
  color: #ffffff;
  margin: 0 auto;
  margin-top: 50px;
  overflow: auto;
}
.btn {
  width: 200px;
  height: 40px;
  line-height: 40px;
  background: blue;
  color: #ffffff;
  text-align: center;
  cursor: pointer;
  margin: 0 auto;
  margin-top: 20px;
}
</style>
