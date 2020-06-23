<template>
  <!-- prettier-ignore -->
  <header class="flex items-center py-4 md:py-8">
    <div class="header__logo">
      <nuxt-link to="/">
        <svg width="80" height="80" xmlns="http://www.w3.org/2000/svg">
           <g>
  <g stroke="null" id="svg_3">
   <text transform="matrix(2.7611606121063232,0,0,2.7611606121063232,-9.025948137044907,-12.025424804538488) " stroke="#000" font-weight="bold" xml:space="preserve" text-anchor="start" font-family="Arvo, sans-serif" font-size="24" id="svg_1" y="27.47599" x="3.58582" stroke-width="0" fill="#999999">A</text>
   <text transform="matrix(2.7611606121063232,0,0,2.7611606121063232,-9.025948137044907,-12.025424804538488) " stroke="#000" font-weight="bold" xml:space="preserve" text-anchor="start" font-family="Arvo, sans-serif" font-size="24" id="svg_2" y="27.47599" x="16.3358" stroke-width="0" fill="#444444">N</text>
  </g>
  <text stroke="#000" transform="matrix(1.2318301075382578,0,0,1.098400831222534,15.124756877288196,-5.770901188254355) " xml:space="preserve" text-anchor="start" font-family="Euphoria, sans-serif" font-size="8" id="svg_4" y="71.06246" x="0.62505" stroke-width="0" fill="#999999">WebSpecialist</text>
 </g>
        </svg>
      </nuxt-link>
    </div>

    <nav class="nav ml-auto">
      <ul class=" flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">
        <li>
          <nuxt-link to="/blog" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
            Blog
          </nuxt-link>
        </li>

        <li
          v-for="(page, index) in pages"
          :key="index"
          class="block font-medium px-4 py-1 md:p-2 lg:px-4"
        >
          <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss">
.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}
</style>
