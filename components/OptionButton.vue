<script setup>
import { ref } from "vue";
const props = defineProps({
  category: {
    type: Object,
    required: true,
  },
});
const { category } = props;
const toggleUser = ref(false);
</script>
<template>
  <button
    @click="toggleUser = !toggleUser"
    :class="[
      toggleUser && 'wrapper__options__button__active',
      'wrapper__options__button',
    ]"
  >
    <Icon
      size="1.5em"
      class="wrapper__options__button__avi"
      :name="category.icon"
    />
    {{ category.name }}
    <Icon
      v-if="!toggleUser"
      size="1.5em"      
      name="clarity:plus-line"
    />

    <Icon
      v-else
      size="1.5em"
      name="iconamoon:check-light"
      color="green"
    />
  </button>
</template>