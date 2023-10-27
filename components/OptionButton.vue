<script setup>
import { ref } from "vue";
const props = defineProps({
  user: {
    type: Array,
    required: true,
  },
});
const { user } = props;
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
      :name="user.icon"
    />
    {{ user.username }}
    <Icon
      v-if="!toggleUser"
      size="1.5em"
      class="wrapper__options__button__plus"
      name="clarity:plus-line"
    />

    <Icon
      v-else
      size="1.5em"
      class="wrapper__options__button__plus"
      name="iconamoon:check-light"
      color="green"
    />
  </button>
</template>