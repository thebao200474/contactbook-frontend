<script>
export default {
  props: {
    contacts: {
      type: Array,
      default: () => [],
    },
    activeIndex: {
      type: Number,
      default: -1,
    },
  },
  emits: ["update:activeIndex"],
};
</script>

<template>
  <ul class="list-group">
    <li
      v-for="(contact, index) in contacts"
      :key="contact._id"
      class="list-group-item"
      :class="{ active: index === activeIndex }"
      @click="$emit('update:activeIndex', index)"
    >
      {{ contact.name }}
    </li>
  </ul>
</template>