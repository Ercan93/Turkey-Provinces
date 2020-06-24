<template>
  <div>
    <h1>Şehir Adı: {{provinceName}}</h1>
  </div>
</template>
<script>
export default {
  props: {
    provinceName: String
  }
};
</script>