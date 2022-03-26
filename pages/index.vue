<template>
  <div class="absolute w-full h-full">
    <div class="container mx-auto px-4 flex justify-center items-center h-full">
      <div class="w-1/2 h-full max-h-full relative flex justify-center items-center">
        <div class="absolute w-3/4 h-full max-h-full text-center flex justify-center items-center">
          <img src="/images/damath-board.png" alt="Damath online game board" class="mx-auto max-h-full max-w-full" />
        </div>
      </div>
      <div class="w-1/2">
        <div class="w-1/2 text-center mx-auto">
          <h2 class="text-[min(max(1.125rem,6vh),2.75rem)] font-bold">Online DAMATH Board Game</h2>
          <div class="flex justify-between my-8" v-show="false">
            <div>
              <span class="font-bold">100</span> <span class="font-medium">online</span>
            </div>
            <div>
              <span class="font-bold">100</span> <span class="font-medium">games today</span>
            </div>
          </div>
          <div class="mt-16">
            <a class="btn btn-primary btn-block btn-lg rounded-box" href="https://game.damath.ph">Play</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import * as SITE_INFO from "~/content/site/info.json";

export default {
  name: 'IndexPage',
  head() {
    const title = SITE_INFO.sitename;
    const description = SITE_INFO.sitedescription || process.env.npm_package_description || '';

    return {
      title,
      meta: [
        { name: 'title', content: title },
        { name: 'description', content: description },
        { property: 'og:title', content: title },
        { property: 'og:description', content: description }
      ]
    }
  }
}
</script>
