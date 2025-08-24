<template>
  <div id="app">
    <Header />
    <main>
      <router-view />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
  components: { Header, Footer }
}
</script>

<style>
body {
  margin: 0;
  font-family: 'Jost', sans-serif;
  background: #f2f2f2; /* светло-серый фон */
  color: #222;
}

html, body, #app {
  height: 100%;          /* растягиваем всё на высоту окна */
  margin: 0;
}

#app {
  display: flex;
  flex-direction: column; /* выстраиваем элементы сверху вниз */
  min-height: 100vh;      /* чтобы занимало всю высоту экрана */
}

main {
  flex: 1;                /* растягиваем контент */
  padding: 20px;
  animation: fadeIn 1s ease-in;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* 📱 Адаптация под телефоны */
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }

  h1 {
    font-size: 20px;
  }

  h2 {
    font-size: 18px;
  }

  main {
    padding: 10px;
  }

  .call-btn {
    font-size: 16px;
    padding: 12px 18px;
  }

  .hero-img {
    max-height: 300px;  /* картинка меньше на мобилке */
  }

  nav a {
    font-size: 14px;
    padding: 6px 10px;
  }

  footer {
    font-size: 12px;
    padding: 8px;
  }
}
</style>