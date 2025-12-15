<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-logo">
        <a href="/">
          <img src="@/assets/img/logo%20small.png" class="navbar-logo">
        </a>
      </div>

      <div class="navbar-links">
        <a href="/#" @click.prevent="$emit('scroll-to-about')">О нас</a>
        <a href="/#" @click.prevent="$emit('scroll-to-clients')">Клиентам</a>
        <a href="/#" @click.prevent="$emit('scroll-to-candidates')">Соискателям</a>
        <a href="/#" @click.prevent="$emit('scroll-to-contacts')">Контакты</a>
      </div>
      <div class="navbar-action">
        <button class="btn">Войти</button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import './NavBar.css'

defineEmits(['scroll-to-about', 'scroll-to-clients', 'scroll-to-candidates', 'scroll-to-contacts'])
</script>
