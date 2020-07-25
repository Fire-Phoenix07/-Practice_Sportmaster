<template>
  <div class="message-item">
    <div class="message-read__state"></div>
    <img class="message-item__person" v-bind:src="person" alt />
    <p class="message-item__person-name">ООО "Спортмастер"</p>
    <div class="message-item__theme-block">
      <p class="message-item__theme-block__placeholder">тема:</p>
      <p class="message-item__theme-block__text">Произодственная практика в ООО "Спортмастер"</p>
    </div>
    <div class="message-item__message-block">
      <p class="message-item__message-block__placeholder">сообщение:</p>
      <p class="message-item__message-block__text">
        - Обновились две формы:
        1. Задание.
        2. Дневник.
        - Добавилась форма титульного листа отчета о практике.
        - Вместо отзыва надо делать два документа:
        1. Аттестационный лист.
        2. Характеристику.
        Формы аттестационого листа и характеристики также добавлены.
        Необходимая информация для заполнения документов: название модуля, количество часов, компетенции - находятся в рабочей программе и методических указаниях.
      </p>
    </div>
    <p class="message-item__time">14:38</p>
  </div>
</template>


<script>
import person from "@/assets/person.svg";

export default {
  name: "message",
  data: function () {
    return {
      person,
    };
  },
};
</script>

