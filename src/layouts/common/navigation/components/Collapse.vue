<template>
  <q-expansion-item
    v-for="data in collapseNavigationItem" :key="data.id"
    :icon="data.icon"
    :label="data.title"
  >
    <q-list class="q-pl-lg">
      <q-item
        v-for="item in data.children" :key="item.id"
        :to="item.link"
        active-class="q-item-no-link-highlighting">
        <q-item-section avatar>
          <q-icon :name="item.icon"/>
        </q-item-section>
        <q-item-section>
          <q-item-label>{{item.title}}</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </q-expansion-item>
</template>

<script>
  export default {
    name: 'Collapse',
    props: ['navigationItem'],
    computed: {
      collapseNavigationItem() {
        return this.navigationItem.children.filter(n => n.type === 'collapse')
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
