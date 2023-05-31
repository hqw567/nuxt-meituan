<script lang="ts" setup>
useHead({
  htmlAttrs: {
    class: '[--scroll-mt:9.875rem] lg:[--scroll-mt:6.3125rem] js-focus-visible',
  },
  bodyAttrs: {
    class: 'antialiased text-slate-600 dark:text-slate-400 bg-white dark:bg-slate-900',
  },
})

// if (process.client) {
//   if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches))
//     document.documentElement.classList.add('dark')

//   else
//     document.documentElement.classList.remove('dark')
// }
</script>

<template>
  <div class="font-sans">
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>
