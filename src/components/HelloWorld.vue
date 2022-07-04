<template>
  <div class="hello">
    本项目是为了复现 iframe + pdf.js 在360浏览器兼容模式白屏的问题。
    <br />
    注释掉<code>node_modules/webpack-dev-server/client/index.js</code>文件中的最后两行<code
      >var socketURL = createSocketURL(parsedResourceQuery);</code
    >和<code>socket(socketURL, onSocketMessage, options.reconnect);</code>
    <br />
    问题复现流程：
    <br />
    1. 页面加载
    <br />
    2.
    点击“浏览”选择一个文件，正常现象会出现一个新的“点击展示pdf”按钮，此时会出现页面白屏
    <br />
    3. 重新加载页面（可以切换到极速模式，再切回兼容模式）
    <br />
    4. 点击“点击展示pdf”，展示pdf，点击右上角的“点击关闭pdf”关闭pdf图层
    <br />
    5.点击“浏览器”选择一个文件，此时正常
    <Block></Block>
    <br />
    <Block v-for="item in list" :key="item"></Block>
    <input ref="file" type="file" accept="*/*" @change="selectFile" />
  </div>
</template>

<script>
import Block from "./Block.vue";
export default {
  name: "HelloWorld",
  components: {
    Block,
  },
  data() {
    return {
      list: [],
    };
  },
  methods: {
    selectFile() {
      this.$refs.file.value = null;
      this.list.push(Math.random());
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
