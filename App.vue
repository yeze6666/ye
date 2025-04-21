<template>
  <header class="doro-header">
    <p><span>Doro</span><span>.pink</span></p>
    <nav>
      <ul>
        <li>
          <router-link to="/" active-class="active">
            <img src="./assets/icons/home.svg" alt="首页" />
            <strong>首页</strong>
          </router-link>
        </li>
        <li>
          <router-link to="/article" active-class="active">
            <img src="./assets/icons/book.svg" alt="文章" />
            <strong>文章</strong>
          </router-link>
        </li>
        <li>
          <router-link to="/picture" active-class="active">
            <img src="./assets/icons/pic.svg" alt="图库" />
            <strong>图库</strong>
          </router-link>
        </li>
        <li>
          <router-link to="/about" active-class="active">
            <img src="./assets/icons/people.svg" alt="关于" />
            <strong>关于</strong>
          </router-link>
        </li>
      </ul>
    </nav>
  </header>

  <main class="doro-main">
    <router-view></router-view>
  </main>
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<style scoped>
.doro-header {
  position: static;
  top: 0;
  width: calc(100vw - 30vw);
  background: rgba(248, 248, 248, 0.98);
  backdrop-filter: blur(8px);
  justify-self: center;
  min-width: 40rem;
  max-width: 80rem;
  padding: 1rem 2rem;
  border-radius: 16px;
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.247);
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 1000;
  border: 1px solid #e8ddee;
}

.doro-header p {
  font-size: 1.8rem;
  font-weight: 700;
  color: #875db4;
  margin: 0;
  letter-spacing: -0.03em;
}

.doro-header p span:last-child {
  color: #FF7A7A;
  margin-left: 0.2rem;
}

nav ul {
  display: flex;
  gap: 1.2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  position: relative;
  padding: 0.8rem 1.2rem;
  border-radius: 10px;
  transition: all 0.2s;
}

nav li:hover {
  background: rgba(255, 93, 141, 0.137);
}

nav a {
  text-decoration: none;
  color: #4A3A5A;
  font-weight: 500;
  display: flex;
  align-items: center;
  gap: 0.6rem;
}

nav img {
  width: 20px;
  height: 20px;
  filter: invert(20%);
}

/* 下划线动画 */
nav a::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background: #FF7A7A;
  transition: all 0.3s;
}

nav li:hover a::after {
  width: 80%;
  left: 10%;
}

/* 激活状态 */
nav a.active {
  color: #000000;
  font-weight: 600;
}

nav a.active::after {
  width: 100%;
  left: 0;
  background: #ee2525;
}

.doro-main {
  justify-self: center;
  padding: 2rem;
  min-height: calc(100vh - 120px);
  background: #fcecf1;
  border-radius: 28px;
  min-width: calc(100vw - 30vw);
}
</style>