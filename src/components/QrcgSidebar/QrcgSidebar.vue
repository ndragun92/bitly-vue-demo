<template>
  <aside>
    <slot>Sidebar placeholder</slot>
  </aside>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

@Component
export default class QrcgSidebar extends Vue {}
</script>

<style lang="scss" scoped>
aside {
  background-color: silver;
  height: 100%;
}
</style>
