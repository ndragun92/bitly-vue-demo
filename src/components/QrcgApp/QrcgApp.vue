<template>
  <div id="qrcg-app">
    <qrcg-navbar class="qrcg-navbar" />
    <div class="qrcg__wrapper" part="qrcg__wrapper">
      <qrcg-sidebar class="qrcg-sidebar" />
      <qrcg-content class="qrcg-content" :data-content="dataContent" @submit="$emit('submit', $event)">
        <slot name="content" />
      </qrcg-content>
    </div>
  </div>
</template>

<script lang="ts">
import '@/assets/styles/main.scss'
import { Vue, Component, Prop } from 'vue-property-decorator'
import QrcgNavbar from '@/components/QrcgNavbar/QrcgNavbar.vue'
import QrcgSidebar from '@/components/QrcgSidebar/QrcgSidebar.vue'
import QrcgContent from '@/components/QrcgContent/QrcgContent.vue'
@Component({
  components: { QrcgContent, QrcgNavbar, QrcgSidebar }
})
export default class QrcgApp extends Vue {
  @Prop({ required: true, type: String, default: 'My default prop data' })
  dataContent!: string
}
</script>

<style lang="scss">
#qrcg-app {
  display: flex;
  flex-direction: column;
  height: 100vh;
}
.qrcg__wrapper {
  flex-grow: 1;
  min-width: 0;
  min-height: 0;
  display: grid;
  grid-template-areas: 'qrcg-sidebar qrcg-content';
  grid-template-columns: 350px minmax(0, 1fr);
  .qrcg-sidebar {
    grid-area: qrcg-sidebar;
  }
  .qrcg-content {
    grid-area: qrcg-content;
  }
}
</style>
