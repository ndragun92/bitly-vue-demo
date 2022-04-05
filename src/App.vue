<template>
  <qrcg-app data-content="Wohoo" />
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import QrcgApp from '@/components/QrcgApp/QrcgApp.vue'
@Component({
  components: { QrcgApp }
})
export default class App extends Vue {}
</script>
