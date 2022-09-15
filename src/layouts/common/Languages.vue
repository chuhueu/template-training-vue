<template>
  <q-btn round>
    <img :src="logoUS" />
    <q-menu
      transition-show="jump-down"
      transition-hide="jump-up"
    >
      <q-list style="min-width: 100px">
        <q-item clickable v-close-popup class="row items-center">
          <span class="row q-pr-sm"><img :src="logoUS" /></span>
          <span>English</span>
        </q-item>
        <q-item clickable v-close-popup class="row items-center">
          <span class="row q-pr-sm"><img :src="logoVI" /></span>
          <span>Việt Nam</span>
        </q-item>
      </q-list>
    </q-menu>
  </q-btn>
</template>

<script>
  import US from 'assets/flags/US.svg'
  import VI from 'assets/flags/VI.svg'
  export default {
    name: 'Languages',
    data: function () {
      return {
        logoUS: US,
        logoVI: VI
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
