<template>
  <header>
    <div class="logo-wrap">
      <img src="/logo.png" alt="Логотип" class="logo" />
      <h1>Эвакуатор Луганск</h1>
    </div>

    <nav>
      <router-link to="/">Главная</router-link>
      <router-link to="/services">Услуги</router-link>
      <router-link to="/about">О нас</router-link>
      <router-link to="/contacts">Контакты</router-link>
    </nav>

    <a class="call-btn" href="tel:+79591486749">📞 Вызвать</a>
  </header>
</template>

<style>
header {
  background: #444; /* тёмно-серый фон */
  padding: 5px 50px; /* ↑ увеличил padding сверху и снизу */
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
  height: 50px;   /* можно менять размер */
  margin-right: 10px;
}

.burger {
  display: none;          /* по умолчанию скрыт */
  font-size: 26px;
  background: none;
  border: none;
  color: white;
  cursor: pointer;
}

@media (max-width: 768px) {
  nav {
    display: none;                 /* скрываем меню по умолчанию */
    flex-direction: column;
    width: 100%;
    text-align: center;
    margin-top: 10px;
  }
  nav.open {
    display: flex;                 /* показываем при клике */
  }
  .burger {
    display: block;                /* показываем кнопку на телефонах */
  }
  .right {
    flex: 0;                       /* кнопка вызова справа не ломает сетку */
  }
}



nav a {
  padding: 8px 12px;
  text-decoration: none;
  color: white;
  background: #666;    /* серый прямоугольник */
  border-radius: 4px;
  transition: 0.3s;
      opacity: 20;
    transform: translateY(10px);
    transition: opacity 0.4s ease, transform 0.4s ease;
}
  nav.open a {
    opacity: 1;
    transform: translateY(0);
  }

    nav.open a:nth-child(1) { transition-delay: 0.1s; }
  nav.open a:nth-child(2) { transition-delay: 0.2s; }
  nav.open a:nth-child(3) { transition-delay: 0.3s; }
  nav.open a:nth-child(4) { transition-delay: 0.4s; }

    .right {
    flex: 0;
  }

nav a:hover {
  background: #888;
}

/* кнопка вызова справа */
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
  background: hsl(0, 0%, 15%);
}

.burger {
  display: none;
  font-size: 26px;
  background: none;
  border: none;
  color: white;
  cursor: pointer;
}

/* адаптив */
@media (max-width: 768px) {
  nav {
    display: flex;
    flex-direction: column;
    width: 100%;
    text-align: center;
    margin-top: 10px;

    max-height: 0;               
    overflow: hidden;
    opacity: 0;
    transition: all 0.4s ease;
  }



  .burger {
    display: block;
  }

  .right {
    flex: 0;
  }
}
</style>