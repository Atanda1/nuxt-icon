<script setup>
import { categories } from "/data/items-list.js";
</script>

<template>
  <div class="wrapper">
    <div class="wrapper__inner">
      <Icon
        class="wrapper__inner__icon"
        name="logos:medium"
        width="7em"
        height="2.5em"
        color="black"
      />
      <h3 class="wrapper__inner__title">What are you interested in?</h3>
      <p class="wrapper__inner__select">Choose three or more.</p>
    </div>
    <div class="wrapper__options">
      <div :key="category.id" v-for="category in categories">
        <OptionButton :category="category" />
      </div>
    </div>
    <div class="wrapper__footer">
      <button class="wrapper__footer__button">Continue</button>
    </div>
  </div>
</template>


