<template>
  <header>
    <!-- Логотип + название -->
    <div class="logo-wrap">
      <img src="/logo.png" alt="Логотип" class="logo" />
      <h1>Эвакуатор Луганск</h1>
    </div>

    <!-- Кнопка гамбургер -->
    <button class="burger" @click="toggleMenu">
      ☰
    </button>

    <!-- Навигация -->
    <nav :class="{ open: isMenuOpen }">
      <router-link to="/" @click="closeMenu">Главная</router-link>
      <router-link to="/services" @click="closeMenu">Услуги</router-link>
      <router-link to="/about" @click="closeMenu">О нас</router-link>
      <router-link to="/contacts" @click="closeMenu">Контакты</router-link>
    </nav>

    <!-- Кнопка вызова -->
    <div class="right">
      <a class="call-btn" href="tel:+79591486749">📞 Вызвать</a>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenu() {
      this.isMenuOpen = false
    }
  }
}
</script>

<style>
header {
  background: #444;
  padding: 10px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  color: white;
}

.logo-wrap {
  display: flex;
  align-items: center;
}
.logo {
  height: 45px;
  margin-right: 10px;
}

/* меню */
nav {
  flex: 1;
  display: flex;
  justify-content: center;
  gap: 10px;
}
nav a {
  padding: 8px 12px;
  text-decoration: none;
  color: white;
  background: #666;
  border-radius: 4px;
  transition: 0.3s;
}
nav a:hover {
  background: #888;
}

/* кнопка вызова */
.right {
  display: flex;
  justify-content: flex-end;
  flex: 1;
}
.call-btn {
  background: #666;
  color: white;
  padding: 10px 20px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  box-shadow: 0 3px 8px rgba(0,0,0,0.3);
  transition: 0.3s;
}
.call-btn:hover {
  background: #888;
}

/* кнопка-гамбургер */
.burger {
  display: none;
  font-size: 26px;
  background: none;
  border: none;
  color: white;
  cursor: pointer;
}

/* 📱 адаптив */
@media (max-width: 768px) {
  nav {
    display: none;
    flex-direction: column;
    width: 100%;
    text-align: center;
    margin-top: 10px;

    max-height: 0;
    overflow: hidden;
    opacity: 0;
    transition: all 0.4s ease;
  }
  nav.open {
    display: flex;
    max-height: 300px;
    opacity: 1;
  }

  /* пункты появляются с каскадом */
  nav.open a {
    opacity: 1;
    transform: translateY(0);
  }
  nav.open a:nth-child(1) { transition-delay: 0.1s; }
  nav.open a:nth-child(2) { transition-delay: 0.2s; }
  nav.open a:nth-child(3) { transition-delay: 0.3s; }
  nav.open a:nth-child(4) { transition-delay: 0.4s; }

  .burger {
    display: block; /* показываем кнопку */
  }

  .right {
    flex: 0;
  }
}
</style>
