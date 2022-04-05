<template>
  <main>
    <h1 part="contant-title">Content</h1>
    <pre>
      {{ dataContent }}
    </pre>
    <div>
      <button type="button" @click="$emit('submit', $event)">Submit</button>
    </div>
    <slot />
  </main>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component
export default class QrcgContent extends Vue {
  @Prop({ required: true, type: String })
  dataContent!: string
}
</script>

<style lang="scss">
main {
  padding: 20px;
}
</style>
