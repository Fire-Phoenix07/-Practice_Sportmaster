<template>
  <div id="app">
    <div class="message-look">
      <div class="message-form">
        <div class="message-form__top">
          <p class="message-form__theme">Производственная практика</p>
          <img class="lock-form__item" v-bind:src="lockItem" alt />
        </div>
        <div class="from-person__block">
          <p class="message-form__theme">От:</p>
          <img class="message-form__person-img" v-bind:src="darkPerson" alt />
          <p class="message-form__person-name">ООО Спортмастер"</p>
        </div>
        <p class="message-place__text">Сообщение:</p>
        <div class="person-message">
          <p>
            - Обновились две формы:
            <br />1. Задание.
            <br />2. Дневник.
            <br />- Добавилась форма титульного листа отчета о практике.
            <br />- Вместо отзыва надо делать два документа:
            <br />1. Аттестационный лист.
            <br />2. Характеристику.
            <br />Формы аттестационого листа и характеристики также добавлены.
            Необходимая информация для заполнения документов: название модуля, количество часов, компетенции - находятся в рабочей программе и методических указаниях.
          </p>
        </div>
        <p class="message-place__text">Ваш ответ:</p>
        <textarea placeholder="Введите сообщение" class="textarea"></textarea>
        <div class="btn-place">
          <div class="send-btn">Отправить</div>
        </div>
      </div>
    </div>
    <header class="header">
      <div class="header-content">
        <div class="header-content__links-block">
          <a href="/" class="header-content__links-block__item">VUE-MESSAGER</a>
          <a href="/" class="header-content__links-block__item">Входящие</a>
          <a href="/" class="header-content__links-block__item">Отправленные</a>
          <a href="/" class="header-content__links-block__item">Черновики</a>
          <a href="/" class="header-content__links-block__item">Спам</a>
          <a href="/" class="header-content__links-block__item">Корзина</a>
        </div>
        <div class="user-exit__block">
          <div class="user-exit__block-user">
            <p class="user-exit__block-user__text">user228</p>
            <img class v-bind:src="userArrow" alt />
          </div>
          <p class="user-exit__block-user__text">выход</p>
        </div>
      </div>
    </header>
    <div class="main-section">
      <img class="main-section__logo" v-bind:src="logo" alt />
      <div class="left-hide__bar">
        <div class="lock-item">
          <span></span>
          <span></span>
        </div>
        <div class="left-hide__bar-item">
          <img class v-bind:src="mail" alt />
          <p>Входящие</p>
        </div>
        <div class="left-hide__bar-item">
          <img class v-bind:src="sends" alt />
          <p>Отправленные</p>
        </div>
        <div class="left-hide__bar-item">
          <img class v-bind:src="doc" alt />
          <p>Черновики</p>
        </div>
        <div class="left-hide__bar-item">
          <img class v-bind:src="dislike" alt />
          <p>Спам</p>
        </div>
        <div class="left-hide__bar-item">
          <img class v-bind:src="basket" alt />
          <p>Корзина</p>
        </div>
      </div>
      <div class="content">
        <div class="white-background__block">
          <div class="top-filter__block">
            <p class="top-filter__block-text">Входящие</p>
            <div class="filter-text__block">
              <p class="top-filter__block-text">Фильтр</p>
              <img class v-bind:src="filter" alt />
            </div>
          </div>
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
          <message />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
document.addEventListener(
  "DOMContentLoaded",
  function () {
    let leftMenu = document.querySelector(".left-hide__bar");
    let lockItem = document.querySelector(".lock-item");
    let lockItemSpan = document.querySelectorAll(".lock-item span");
    let messages = document.querySelectorAll(".message-item");
    let messageBlock = document.querySelector(".message-look");
    let lockMessage = document.querySelector('.lock-form__item')


    for (let i = 0; i < messages.length; i++) {
      messages[i].onclick = function () {
        messageBlock.style.top = "0";
      };
    }

    lockMessage.onclick=function(){
       messageBlock.style.top = "-100%";
    }

    lockItem.onclick = function () {
      if (leftMenu.style.left == "-6%" || leftMenu.style.left == "") {
        leftMenu.style.left = "0";
        lockItemSpan[1].style.top = "0";
      } else {
        leftMenu.style.left = "-6%";
        lockItemSpan[1].style.top = "0.5rem";
      }
    };
  },
  false
);

import userArrow from "@/assets/user-arrow.svg";
import logo from "@/assets/logo.svg";
import lockItem from "@/assets/lock-item.svg";
import mail from "@/assets/mail.svg";
import sends from "@/assets/sends.svg";
import doc from "@/assets/doc.svg";
import dislike from "@/assets/dislike.svg";
import basket from "@/assets/basket.svg";
import filter from "@/assets/filter.svg";
import darkPerson from "@/assets/dark-person.svg";

import message from "@/components/message";

export default {
  name: "App",
  components: { message },
  data: function () {
    return {
      userArrow,
      logo,
      lockItem,
      mail,
      sends,
      doc,
      dislike,
      basket,
      filter,
      darkPerson,
    };
  },
};
</script>

