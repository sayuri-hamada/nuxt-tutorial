<template>
  <div>
    <h1>About Page</h1>
    <h2>{{subTitle}}</h2>
  </div>

</template>

<script>
export default {
  layout: "original",
  data() {
    return {
      subTitle: "この文章はNuxt.jsの基本的な使用方法について説明しています。"
    }
  }
};
</script>
