<template>
  <Header />
  <UserDetail />
  <Footer />
</template>

<script>
  import { defineAsyncComponent } from 'vue';
  import UserDetail from './pages/UserDetail';

  export default {
    name: 'App',
    components: {
      Header: defineAsyncComponent(() => import('mfVueShell/Header')),
      Footer: defineAsyncComponent(() => import('mfVueShell/Footer')),
      UserDetail
    }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>