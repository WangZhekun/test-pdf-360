<template>
  <div class="block">
    <button @click="showPDF = true">点击展示pdf</button>
    <iframe
      class="pdf-viewer"
      v-show="showPDF"
      src="/generic-v1-4/web/viewer.html?file=/test.pdf"
    ></iframe>
    <button class="pdf-close-btn" @click="showPDF = false">点击关闭pdf</button>
  </div>
</template>

<script>
export default {
  name: "file-block",
  props: {
    msg: String,
  },
  data() {
    return {
      showPDF: false,
    };
  },
};
</script>

<style scoped lang="less">
.pdf-viewer {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 100;
  width: 100%;
  height: 100%;
}
.pdf-close-btn {
  position: fixed;
  top: 0;
  right: 0;
  z-index: 101;
}
</style>
