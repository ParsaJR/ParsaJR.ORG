<script setup lang="ts">
const colorMode = useColorMode();

import { useRoute } from "vue-router";

const route = useRoute();
const pathWithSlash = route.path.endsWith("/") ? route.path : `${route.path}/`;
const canonical = `https://parsajr.org${pathWithSlash}`;

useHead({
  link: [
    { rel: "icon", type: "image/x-icon", href: "/favicon.ico" },
    { rel: "canonical", href: canonical },
  ],
});

useHead({});

function toggleColorTheme() {
  switch (colorMode.preference) {
    case "light":
      colorMode.preference = "dark";
      break;
    case "dark":
      colorMode.preference = "light";
      break;
    default:
      colorMode.preference = "dark";
      break;
  }
}
</script>
<template>
  <NuxtLoadingIndicator color="#00dc82" :throttle="100" />
  <div class="container max-w-5xl mx-auto px-8 w-screen h-full">
    <header class="pt-6 pb-8 flex justify-between">
      <div class="inline-block">
        <ul class="list-none flex items-center gap-2 text-base lg:text-lg">
          <NuxtLink to="/">
            <li class="inline-flex justify-center">Parsa Junior</li>
          </NuxtLink>

          <button aria-label="toggle color theme" @click="toggleColorTheme">
            <li class="inline-flex justify-center">
              <Icon
                v-if="colorMode.preference === 'dark'"
                name="i-material-symbols:mode-night"
                size="30px"
              ></Icon>
              <Icon v-else name="i-material-symbols:wb-sunny" size="30px">
              </Icon>
            </li>
          </button>
        </ul>
      </div>
      <div>
        <ul class="list-none flex items-center gap-4 text-base lg:text-lg">
          <li class="inline-flex">
            <!-- <icon name="i-twemoji:flag-iran" size="30px"></icon> -->
          </li>
          <NuxtLink to="/blogs">
            <li class="inline-flex">Blog</li>
          </NuxtLink>
          <NuxtLink to="/about">
            <li class="inline-flex">About</li>
          </NuxtLink>
          <NuxtLink :external=true target="_blank" to="https://status.parsajr.org">
            <li class="inline-flex">Status</li>
          </NuxtLink>
        </ul>
      </div>
    </header>
    <div>
      <NuxtPage />
    </div>
  </div>
  <footer class="p-3">
    <div class="flex justify-center gap-5">
      <a title="Github Account" href="https://github.com/ParsaJR">
        <Icon name="i-grommet-icons-github" size="1.5rem"></Icon>
      </a>
      <a title="Contact me" href="mailto:hi@parsajr.org">
        <Icon name="i-grommet-icons-mail" size="1.5rem"></Icon>
      </a>
    </div>
    <div
      class="container mx-auto max-w-5xl flex items-center justify-center px-10 py-2"
    >
      <p class="text-xs md:text-sm">Parsa • © 2025 • No Right is reserved.</p>
    </div>
    <div
      class="container mx-auto max-w-5xl flex items-center justify-center px-10"
    >
      <p class="text-xs md:text-sm">
        Powered By 
        <a href="https://nuxt.com">
          <Icon name="i-logos-nuxt-icon"></Icon>
        </a>
      </p>
    </div>
  </footer>
</template>

<style scoped>
a > li:hover {
  text-decoration: underline;
}
</style>
