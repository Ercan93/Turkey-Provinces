<template>
  <div class="container">
    <h1 class="province-title">Şehir Adı: {{provinceName}}</h1>
    <iframe :src="'https://tr.wikipedia.org/wiki/'+provinceName+'_(il)'" class="province-wiki-page"></iframe>
  </div>
</template>
<script>
export default {
  props: {
    provinceName: String
  }
};
</script>
<style scoped>
.container {
  height: 100vh;
}
.province-wiki-page {
  width: 90vw;
  height: 95vh;
  box-sizing: border-box;
  border-radius: 15px;
}
.province-title {
  color: white;
  height: 5vh;
}
</style>