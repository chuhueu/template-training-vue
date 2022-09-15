<template>
  <q-item
    v-for="data in basicNavigationItem" :key="data.id"
    :to="data.link"
    active-class="q-item-no-link-highlighting">
    <q-item-section avatar>
      <q-icon :name="data.icon" />
    </q-item-section>
    <q-item-section>
      <q-item-label>{{data.title}}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
  export default {
    name: 'Basic',
    props: ['navigationItem'],
    computed: {
      basicNavigationItem() {
        return this.navigationItem.children.filter(n => n.type === 'basic')
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
