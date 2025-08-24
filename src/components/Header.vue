<template>
  <header>
    <!-- Логотип -->
    <div class="logo-wrap">
      <img src="/logo.png" alt="Логотип" class="logo" />
      <h1>Эвакуатор Луганск</h1>
    </div>

    <!-- Бургер -->
    <button class="burger" :class="{ active: isMenuOpen }" @click="toggleMenu">
      <span></span>
      <span></span>
      <span></span>
    </button>

    <!-- Навигация (мобильная версия выпадает поверх) -->
    <div class="mobile-menu" v-if="isMenuOpen">
      <div class="overlay" @click="closeMenu"></div>
      <nav class="menu">
        <router-link to="/" @click="closeMenu">Главная</router-link>
        <router-link to="/services" @click="closeMenu">Услуги</router-link>
        <router-link to="/about" @click="closeMenu">О нас</router-link>
        <router-link to="/contacts" @click="closeMenu">Контакты</router-link>
      </nav>
    </div>

    <!-- Кнопка вызова -->
    <div class="right">
      <a class="call-btn" href="tel:+79591486749">📞Вызвать</a>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return { isMenuOpen: false }
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
  color: white;
  position: relative;
  z-index: 10;
}

.logo-wrap {
  display: flex;
  align-items: center;
}
.logo {
  height: 40px;
  margin-right: 10px;
}

/* бургер */
.burger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 26px;
  height: 20px;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 20;
}
.burger span {
  height: 3px;
  background: white;
  border-radius: 3px;
  transition: 0.3s;
}
.burger.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}
.burger.active span:nth-child(2) {
  opacity: 0;
}
.burger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

/* кнопка вызова */
.right {
  display: flex;
}
.call-btn {
  background: #666;
  color: white;
  padding: 10px 18px;
  border-radius: 6px;
  text-decoration: none;
  font-weight: 600;
  box-shadow: 0 3px 8px rgba(0,0,0,0.3);
  transition: 0.3s;
}
.call-btn:hover {
  background: #888;
}

/* мобильное меню */
.mobile-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 15;
}
.mobile-menu .overlay {
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
}
.mobile-menu .menu {
  position: absolute;
  top: 0;
  right: 0;
  width: 75%;
  max-width: 280px;
  height: 100%;
  background: #333;
  display: flex;
  flex-direction: column;
  padding: 80px 20px;
  gap: 15px;
  transform: translateX(100%);
  animation: slideIn 0.3s forwards;
}
.mobile-menu .menu a {
  color: white;
  text-decoration: none;
  font-size: 18px;
  padding: 10px;
  background: #444;
  border-radius: 4px;
  opacity: 0;
  animation: fadeIn 0.5s forwards;
}
.mobile-menu .menu a:nth-child(1) { animation-delay: 0.1s; }
.mobile-menu .menu a:nth-child(2) { animation-delay: 0.2s; }
.mobile-menu .menu a:nth-child(3) { animation-delay: 0.3s; }
.mobile-menu .menu a:nth-child(4) { animation-delay: 0.4s; }

@keyframes slideIn {
  to { transform: translateX(0); }
}
@keyframes fadeIn {
  to { opacity: 1; }
}

/* адаптив */
@media (max-width: 768px) {
  .burger { display: flex; }
  nav { display: none; } /* убираем десктопное меню */
}
</style>
