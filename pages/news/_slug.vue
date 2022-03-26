<template>
  <div class="absolute h-full w-full overflow-y-auto">
    <div class="container mx-auto px-4 my-8 overflow-auto">
      <article class="w-9/12 mx-auto">
        <img v-if="post.cover" class="cover-image" :src="post.cover" />
        <h1 class="text-4xl mb-8">{{ post.title }}</h1>
        <nuxt-content :document="post" class="prose mx-auto max-w-none" />
      </article>
    </div>
  </div>
</template>

<script>
import * as SITE_INFO from "~/content/site/info.json";

export default {
  async asyncData({ $content, params, error }) {
    let post;
    try {
      post = await $content("news", params.slug).fetch();
    } catch (e) {
      error({ message: "Project not found" });
    }
    return { post };
  },

  head() {
    const title = `${this.post.title} - ${SITE_INFO.sitename}`;
    const description = this.post.description || SITE_INFO.sitedescription || process.env.npm_package_description || '';

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
