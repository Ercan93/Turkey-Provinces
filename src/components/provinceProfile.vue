<template>
  <div>
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
.province-wiki-page {
  width: 90vw;
  height: 800px;
  box-sizing: border-box;
  border-radius: 15px;
}
.province-title {
  color: white;
}
</style>