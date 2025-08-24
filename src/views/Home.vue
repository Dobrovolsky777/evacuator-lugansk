<template>
  <section class="hero">
    <div class="overlay"></div>
    <div class="hero-content">
      <h2>Быстрая помощь на дороге</h2>
      <p>Эвакуатор в Луганске и области, круглосуточно.</p>
      <a class="call-btn" href="tel:+79999999999">📞 Вызвать сейчас</a>
    </div>
    <img class="hero-img" src="/evacuator.jpg" alt="Эвакуатор">
  </section>
</template>

<style>
.hero {
  position: relative;
  text-align: center;
  color: white;
  overflow: hidden;
}

.hero-img {
  width: 100%;
  height: 2000px;
  object-fit: cover;
  filter: brightness(60%);
  max-height: 700px;
}

.overlay {
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.4);
}

.hero-content {
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  animation: fadeIn 1.2s ease-in;
}

/* кнопка вызова */
.call-btn {
  display: inline-block;
  margin-top: 20px;
  background: hwb(123 42% 34%);          /* серый фон */
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
  background: #414141;
}
</style>
