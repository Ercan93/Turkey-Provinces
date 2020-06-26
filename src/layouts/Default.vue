<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link class="site-name" to="/">Türkiye İller haritası</g-link>
      </strong>
      <nav class="nav">
        <g-link to="/About">Hakkında</g-link>
      </nav>
    </header>
    <slot />
  </div>
</template>

<style>
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

.layout {
  margin: 0 auto;
  background-color: rgb(13, 6, 27);
}

.header {
  display: flex;
  justify-content: center;
  font-size: 3rem;
  align-items: center;
  height: 10vh;

  color: #128576;
}

.nav {
  margin-left: auto;
  padding: 10px 20px;
}
.nav > * {
  text-decoration: none;
  color: #128576;
}
.site-name {
  text-decoration: none;
  color: #b9fff6;
}
</style>
