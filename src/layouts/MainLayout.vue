<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar
        class="bg-white q-py-md"
        :class="{
          'justify-between': $q.screen.lt.md,
          'justify-end': $q.screen.gt.sm
        }"
      >
        <q-btn
          v-if="$q.screen.lt.md"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          color="primary"
          size="lg"
        />

        <div class="user-details">
          <q-avatar
            color="accent"
            text-color="white"
            class="q-mr-sm"
          >NK</q-avatar>
          <div class="text-black text-h6 float-right">Nathan Keller</div>
        </div>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      class="bg-primary text-white"
    >
      <q-list>
        <q-item-label
          header
        >
          <q-img src="../assets/trading_company_logo.png"/>
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Home',
    icon: 'home',
    link: '/home'
  },
  {
    title: 'Transfer',
    icon: 'swap_horiz',
    link: '/'
  },
  {
    title: 'Account',
    icon: 'switch_account',
    link: '/account'
  },
  {
    title: 'Documents',
    icon: 'description',
    link: 'documents'
  },
  {
    title: 'Reports',
    icon: 'area_chart',
    link: 'reports'
  }
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>

<style lang="scss" scoped>
  .user-details {
    display: flex;
    align-items: center;
  }
</style>
