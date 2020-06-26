<template>
  <Layout>
    <div class="container">
      <p>Türkiye'nin 81 ilini haritadan seçip wikipedia sayfalarını görüntüleyebileceğiniz bir uygulama.</p>
      <a class="github-source" href="https://github.com/Ercan93/Turkey-Provinces">
        <img src="../../static/github-logo.png" alt />
      </a>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "About"
  }
};
</script>
<style scoped>
.container {
  width: 100%;
  height: calc(90vh);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}
.container > p {
  font-size: 2rem;
  padding-top: 30vh;
  text-align: center;
}
.github-source {
  margin-bottom: 30px;
}
</style>