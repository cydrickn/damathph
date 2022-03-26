<template>
  <div class="absolute h-full w-full overflow-y-auto">
    <div class="container mx-auto px-4 my-8 overflow-auto">
      <article class="w-9/12 mx-auto">
        <h1 class="text-4xl mb-8">{{ rules.title }}</h1>
        <nuxt-content :document="rules" class="prose mx-auto max-w-none" />
      </article>
    </div>
  </div>
</template>

<script>
import * as SITE_INFO from "~/content/site/info.json";

export default {
  name: 'RulesPage',

  async asyncData({ $content, params, error }) {
    let rules;
    try {
      rules = await $content("pages", 'rules').fetch();
    } catch (e) {
      error({ message: "Blog post not found" });
    }
    return { rules };
  },

  head() {
    const title = 'Rules - ' + SITE_INFO.sitename;
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

<style scoped>

</style>
