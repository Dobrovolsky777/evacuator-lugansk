<template>
  <section class="hero">
    <div class="overlay"></div>
    <div class="hero-content">
      <h2>Быстрая помощь на дороге</h2>
      <p>Эвакуатор в Луганске и области, круглосуточно.</p>
      <a class="call-btn" href="tel:+79591486749">📞 Вызвать сейчас</a>
    </div>
  </section>
</template>

<style>
.hero {
  position: relative;
  width: 100%;
  height: 75vh; /* на всю высоту экрана */
  background: url('/evacuator.jpg') center center / cover no-repeat; /* фон */
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  color: white;
}

.overlay {
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.4); /* затемнение */
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 600px;
  padding: 20px;
}

.hero-content h2 {
  font-size: 32px;
  margin-bottom: 10px;
}
.hero-content p {
  font-size: 18px;
  margin-bottom: 20px;
}

.call-btn {
  display: inline-block;
  background: #666;
  color: white;
  padding: 15px 25px;
  border-radius: 6px;
  text-decoration: none;
  font-size: 20px;
  font-weight: 600;
  box-shadow: 0 4px 10px rgba(0,0,0,0.4);
  transition: 0.3s;
}
.call-btn:hover {
  background: #888;
}

/* адаптив для телефонов */
@media (max-width: 768px) {
  .hero-content h2 {
    font-size: 22px;
  }
  .hero-content p {
    font-size: 14px;
  }
  .call-btn {
    font-size: 16px;
    padding: 12px 18px;
  }
}
</style>
