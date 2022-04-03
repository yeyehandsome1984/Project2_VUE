<template>
  <div id="wangeditor">
    <div ref="editorElem" style="text-align:left;"></div>
  </div>
</template>

<script>
import E from "wangeditor";
export default {
  name: "Editor",
  data() {
    return {
      editor: null,
      editorContent: ''
    };
  },

  mounted() {
    this.editor = new E(this.$refs.editorElem);
    // Editor event, which the event will refresh when there is an update
    this.editor.config.onchange = this.contentChange
    this.editor.config.menus = [
      // 菜单配置
      'head', // 标题
      'bold', // 粗体
      'fontSize', // 字号
      'fontName', // 字体
      'italic', // 斜体
      'underline', // 下划线
      'strikeThrough', // 删除线
      'foreColor', // 文字颜色
      'backColor', 
      'link', 
      'list', 
      'justify', 
      'quote', 
      'emoticon', 
      'image', 
      'table', 
      'code', 
      'undo', 
      'redo' 
    ];
    this.editor.create(); // 创建富文本实例
  },
  methods: {
    contentChange(html) {
    this.editorContent = html;
    this.$emit('contentChange', this.editorContent); 
    }
  }
}
</script>