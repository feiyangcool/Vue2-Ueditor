<template>
  <div>
    <script :id=id type="text/plain"></script>
  </div>
</template>
<script>
import '../../../static/UE/ueditor.config.js'
import '../../../static/UE/ueditor.all.js'
import '../../../static/UE/lang/zh-cn/zh-cn.js'
import '../../../static/UE/ueditor.parse.min.js'
import '../../../static/UE/themes/default/css/ueditor.css'
// import '../../../static/UE/third-party/zeroClipboard/ZeroClipboard.js'

  export default {
    data () {
      return {
        editor: null
      }
    },
    props: {
      defaultMsg: {
        type: String
      },
      config: {
        type: Object
      },
      id: {
        type: String
      },
    },
    mounted() {
      const _this = this;
      this.editor = window.UE.getEditor(this.id, this.config); // 初始化UE
      this.editor.addListener("ready", function () {
        _this.editor.setContent(_this.defaultMsg); // 确保UE加载完成后，放入内容。
      });
    },
    methods: {
      getUEContent() { // 获取内容方法
        return this.editor.getContent()
      },
      getUEContentTxt() { // 获取纯文本内容方法
        return this.editor.getContentTxt()
      }
    },
    destroyed() {
      this.editor.destroy();
    }
  }
</script>
