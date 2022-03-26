<template>
  <div class="min-h-screen flex flex-col main-app">
    <div>
      <div class="navbar bg-neutral text-neutral-content shadow-xl border-b-primary border-b-8">
        <div class="navbar-start">
          <div class="mx-4"><img src="/images/damath.svg" class="w-8" alt="Damath" /></div>
          <h1 class="text-xl font-bold"><a href="/">Damath Online Game</a></h1>
        </div>
        <div class="navbar-center">
          <a class="btn btn-ghost" href="/">Home</a>
          <a class="btn btn-ghost" href="/community">Community</a>
          <a class="btn btn-ghost" href="/rules">Rules</a>
          <a class="btn btn-ghost" href="/news">News & Events</a>
        </div>
        <div class="navbar-end"></div>
      </div>
    </div>
    <div class="grow relative">
      <nuxt />
    </div>
    <div class="bg-neutral text-neutral-content py-2 border-t-primary border-t-8">
      <div class="container mx-auto flex">
        <div class="grow"><span class="badge badge-primary">Beta</span></div>
        <div class="text-center">
          <a class="link link-hover mx-2" href="/faq">FAQ</a>
          <a class="link link-hover mx-2" href="/privacy">Privacy</a>
          <a class="link link-hover mx-2" href="/about">About</a>
        </div>
        <div class="grow"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout'
}
</script>

<style scoped>

</style>
