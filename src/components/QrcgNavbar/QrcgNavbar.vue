<template>
  <nav class="nav" part="nav">
    <div class="nav--left" part="nav--left">
      <img src="https://docrdsfx76ssb.cloudfront.net/static/1648829780/pages/wp-content/uploads/2021/08/bitly_logo.svg" alt="Logo">
      <sup>Microfrontends <b>Demo</b></sup>
    </div>
    <div part="nav--right">
      <slot>
        <ul class="nav__links">
          <li>
            <a href="/">Home</a>
          </li>
          <li>
            <a href="/about">About</a>
          </li>
        </ul>
      </slot>
    </div>
  </nav>
</template>

<script lang="ts">
import '@/assets/styles/main.scss'
import { Vue, Component } from 'vue-property-decorator'

@Component
export default class QrcgNavbar extends Vue {}
</script>

<style lang="scss" scoped>
.nav {
  height: 60px;
  background-color: var(--nav-bg-color, #000);
  color: var(--nav-text-color, #fff);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
  &--left {
    display: flex;
    gap: 5px;
  }
  img {
    width: 60px;
    display: block;
  }
  sup {
    text-transform: uppercase;
    font-size: 12px;
  }
  &__links {
    display: flex;
    padding: 0;
    margin: 0;
    list-style: none;
    gap: 20px;
    li {
      a {
        text-decoration: none;
        color: var(--nav-text-color, orange);
      }
    }
  }
}
</style>
