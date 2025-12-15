<template>
  <footer class="footer">
  <div class="footer-container">
    <div class="footer-brand">
      <h3>ООО Апогей</h3>
      <p>
        IT‑поддержка и решения для госсектора.<br>
        Помогаем быстро и по делу.
      </p>
    </div>

    <div class="footer-links">
      <a href="#" @click.prevent="$emit('scroll-to-about')">О компании</a>
      <a href="#" @click.prevent="$emit('scroll-to-clients')">Клиентам</a>
      <a href="#" @click.prevent="$emit('scroll-to-candidates')">Соискателям</a>
      <a href="#" @click.prevent="$emit('scroll-to-contacts')">Контакты</a>
    </div>

    <div class="footer-contacts">
      <p>📞 +7 (999) 123‑45‑67</p>
      <p>✉️ info@apogey.ru</p>
      <a href="#" class="footer-btn">Задать вопрос</a>
    </div>
  </div>

  <div class="footer-bottom">
    © 2025 ООО Апогей. Все права защищены.<br> Made by Egor Kuznetcov
  </div>
</footer>
</template>

<script setup>
import "./footer.css"

defineEmits(['scroll-to-about', 'scroll-to-clients', 'scroll-to-candidates', 'scroll-to-contacts'])

</script>