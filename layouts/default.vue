<template>
  <div class="app">
    <Header />
    <main class="app-main">
      <NuxtPage />
    </main>
    <FooterTotal />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import FooterTotal from '@/components/FooterTotal.vue';
export default { components: { Header, FooterTotal } }
</script>