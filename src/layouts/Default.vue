<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link class="site-name" to="/">{{ $static.metadata.siteName }}</g-link>
      </strong>
      <nav class="nav"></nav>
    </header>
    <slot />
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

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
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
  background-color: rgb(13, 6, 27);
  color: #128576;
}

.nav__link {
  margin-left: 20px;
}
.site-name {
  text-decoration: none;
  color: #b9fff6;
}
</style>
