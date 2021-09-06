<template>
  <q-item
    clickable
    tag="a"
    :to="link"
    class="q-py-md"
  >
    <q-item-section
      v-if="icon"
      avatar
    >
      <q-icon
        :name="icon"
        size="md"
      />
    </q-item-section>

    <q-item-section>
      <q-item-label class="text-h6">{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'EssentialLink',
  props: {
    title: {
      type: String,
      required: true
    },

    caption: {
      type: String,
      default: ''
    },

    link: {
      type: String,
      default: '#'
    },

    icon: {
      type: String,
      default: ''
    }
  }
})
</script>

<style lang="scss" scoped>
  .q-item.q-router-link--active, .q-item--active {
    background-color: $cyan-5;
    color: #fff;
  }
</style>
