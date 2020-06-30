<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link class="site-name" to="/">Türkiye İller haritası</g-link>
      </strong>
      <nav class="nav">
        <g-link to="/about">Hakkında</g-link>
      </nav>
    </header>
    <transition name="fade" appear>
      <slot />
    </transition>
  </div>
</template>

<style>
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.layout {
  margin: 0 auto;
  background-color: rgb(13, 6, 27);
}

.header {
  display: flex;
  justify-content: center;
  font-size: 2rem;
  align-items: center;
  height: 10vh;
  color: #128576;
}

.nav {
  margin-left: auto;
  font-size: 1.2rem;
  padding: 10px 20px;
}
.nav > * {
  text-decoration: none;
  color: #128576;
}
.site-name {
  text-decoration: none;
  padding: 10px 20px;
  color: #b9fff6;
}
.fade-enter-active {
  transition: opacity 2s;
}

.fade-enter {
  opacity: 0;
}
.fade-leave {
  opacity: 1;
}
.fade-leave-active {
  transition: opacity 2s;
}
</style>
