<script setup>
import { RouterLink, RouterView } from 'vue-router'
import {ref} from "vue";

import NavBar from '@/components/NavBar/NavBar.vue'
import Carousel from "@/components/Carousel/Carousel.vue";
import Footer from "@/components/Footer/Footer.vue";

import '@/assets/css/hero.css'
import '@/assets/css/cards.css'
import '@/assets/css/main.css'
import '@/assets/css/candidate.css'
import '@/assets/css/icons_carousel.css'
import '@/assets/css/clients.css'
import '@/assets/css/reviews.css'

import { items } from '@/components/IconsCarousel/script.js'

const activeItem = ref(items[0])
function showItem(item) {
  activeItem.value = item
}

const go = () => {
  window.open('https://2gis.ru/krasnoyarsk/firm/985690700195522/tab/reviews?m=92.865436%2C56.012032%2F16.65', '_blank')
}

const clientsBlock = ref(null)
const candidatesBlock = ref(null)
const contactsBlock = ref(null)
const aboutBlock = ref(null)

function scrollToClients() {
  clientsBlock.value?.scrollIntoView({
    behavior: 'smooth'
  })
}

function scrollToCandidates() {
  candidatesBlock.value?.scrollIntoView({
    behavior: 'smooth'
  })
}

function scrollToContacts() {
  contactsBlock.value?.scrollIntoView({
    behavior: 'smooth'
  })
}

function scrollToAbout() {
  aboutBlock.value?.scrollIntoView({
    behavior: 'smooth'
  })
}

</script>

<template>

  <NavBar @scroll-to-about="scrollToAbout"
          @scroll-to-candidates="scrollToCandidates"
          @scroll-to-clients="scrollToClients"
          @scroll-to-contacts="scrollToContacts"/>
  <div class="hero" ref="aboutBlock">
    <div class="carousel">
      <div class="carousel-text-wrapper">
        <div class="carousel-text">

          <img src="@/assets/img/logo.png"/>

          <div class="buttons">
            <div class="hero-action">
              <button class="btn" @click="scrollToClients">Получить консультацию</button>
            </div>

            <div class="hero-action">
              <button class="btn" @click="scrollToCandidates">Стать частью команды</button>
            </div>
          </div>

        </div>
      </div>
      <Carousel />
    </div>

    <div class="cards">
      <div class="cards-wrapper">
        <div class="card">
          <img src="@/assets/img/star.svg">
          <div class="card-text">
            <h1>15 лет на рынке</h1>
            <p>3000+ госучреждений по всей России от Калининграда до Камчатки. №7 среди 6800 партнеров программы 1С.</p>
          </div>
        </div>

        <div class="card">
          <img src="@/assets/img/student.svg">
          <div class="card-text">
            <h1>Растим IT-специалистов</h1>
            <p>550+ сотрудников в 6 городах. Сотрудничаем с ведущими вузами, даем стажировки и карьерный старт.</p>
          </div>
        </div>

        <div class="card">
          <img src="@/assets/img/wrench.svg">
          <div class="card-text">
            <h1>Решаем нерешаемое</h1>
            <p>>500 000 задач решено в 2024 году. Специализируемся именно на бухучете в госучреждениях.</p>
          </div>
        </div>

        <div class="card">
          <img src="@/assets/img/target.svg">
          <div class="card-text">
            <h1>Наша цель: Стать №1</h1>
            <p>Наша амбиция - стать главным партнером для госсектора и лучшим работодателем для IT-специалистов.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="candidate" ref="candidatesBlock">
      <div class="candidate-image">
        <img src="@/assets/img/candidate.jpg">
      </div>
      <div class="candidate-text">
        <div class="candidate-header">
          <h1>Пройдите анкету и узнайте, <br> на какую должность Вы нам подходите!</h1>
        </div>

        <div class="candidate-form">
          <div class="candidate-question">
          К вам обращается главный бухгалтер из Якутии с криком: «В 1С всё полетело после обновления, отчет не сдается!». Ваша первая реакция?
          </div>
          <div class="candidate-button-block">

            <div class="candidate-button">
              <button>
                А) «Прекрасно! Люблю сложные задачи. Сейчас погружусь в логи, найду конфликт обновлений и напишу патч. Это же детектив!»
              </button>
            </div>

            <div class="candidate-button">
              <button>
                Б) «Спокойно, всё решаемо. Давайте по шагам: сначала скриншот ошибки, потом журнал регистрации. Я задам вам 3 точных вопроса, и мы поймем корень проблемы.»
              </button>
            </div>

            <div class="candidate-button">
              <button>
                В) «Не переживайте, вы не одни! Я уже связываюсь с нашим техспецом по обновлениям, параллельно ищу похожий кейс в нашей базе решений. Через 10 минут дам четкий план.»
              </button>
            </div>

          </div>
        </div>
      </div>
    </div>

    <div class="clients" ref="clientsBlock">
      <div class="clients-cards-wrapper">
        <div class="features">
          <div class="icons">
            <div
              v-for="(item, index) in items"
              :key="index"
              class="icon"
              @mouseenter="showItem(item)"
            >
              <img :src="item.icon" alt="" />
            </div>
          </div>

          <div class="text">
            <h2>{{ activeItem.title }}</h2>
            <p>{{ activeItem.text }}</p>
          </div>
        </div>
      </div>

      <div class="clients-task">
        <div class="clients-task-image">
          <img src="@/assets/img/clients.jpg">
        </div>

        <div class="clients-task-content">
          <div class="clients-task-text">
            <h1>Задайте Ваш вопрос и получите решение абсолютно бесплатно и в кратчайшие сроки!</h1>
            <p>
              Оставьте свой вопрос в нашей форме, и наши специалисты оперативно подготовят для вас
              индивидуальное решение. Мы учитываем все нюансы вашей ситуации и гарантируем точный и понятный ответ.
              Получите помощь бесплатно, без лишней бюрократии и ожидания – ваш вопрос будет обработан
              ближайшее время, чтобы вы могли сразу действовать.
            </p>
          </div>

          <div class="clients-task-form">
            <div class="clients-task-form-text">
              <h2>Введите текст вашего обращения.</h2>
            </div>

            <div class="clients-task-form-input">
              <textarea placeholder="Введите вопрос"></textarea>
            </div>

            <div class="clients-task-form-button">
              <button>Оставить заявку</button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="reviews">
      <h1>Отзывы наших клиентов:</h1>
      <div class="review-card">
        <div class="review-avatar"></div>

        <div class="review-content">
          <p class="review-text">
            Отличная команда. Помогли разобраться со сложной ситуацией в 1С,
            всё объяснили человеческим языком и быстро решили проблему.
          </p>

          <span class="review-name">Иван Петров</span>
        </div>
      </div>

      <div class="review-card">
        <div class="review-avatar"></div>

        <div class="review-content">
          <p class="review-text">
            Очень понравился подход — чувствуется опыт именно в госсекторе.
            Ответ получили в тот же день.
          </p>
          <span class="review-name">Мария Соколова</span>
        </div>
      </div>

      <div class="review-card">
        <div class="review-avatar"></div>

        <div class="review-content">
          <p class="review-text">
            Хочу поблагодарить и сказать ОГРОМНОЕ СПАСИБО компании Апогей, и лично Илье Сорока,
            за проявленную оперативную помощь, отзывчивость и профессионализм в поставленной задаче!
            С уважением, заведующий детским садом №22 города Новосибирска Киселева Е.М.
          </p>
          <span class="review-name">Елена Киселева</span>
        </div>
      </div>

      <div class="review-button">
        <button @click="go">Больше отзывов</button>
      </div>
    </div>

    <span ref="contactsBlock"></span>
    <Footer @scroll-to-about="scrollToAbout"
            @scroll-to-candidates="scrollToCandidates"
            @scroll-to-clients="scrollToClients"
            @scroll-to-contacts="scrollToContacts" />

  </div>

</template>