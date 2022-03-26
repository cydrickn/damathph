<template>
  <div class="absolute h-full w-full overflow-y-auto">
    <div class="container mx-auto px-4 my-8 overflow-auto">
      <div class="w-9/12 mx-auto">
        <h1 class="text-4xl mb-8">News and Updates</h1>
        <div class="grow grid grid-cols-3 gap-4">
          <div v-for="(post, key) in posts" :key="key">
            <a :href="`/news/${post.slug}`" class="card card-bordered rounded-box">
              <div class="card-body">
                <h2 class="card-title">{{ post.title }}</h2>
                <h3 class="text-accent">{{ formatDate(post.createdAt) }}</h3>
                <p>{{ post.description }}</p>
              </div>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import * as SITE_INFO from "~/content/site/info.json";

export default {
  async asyncData({ $content, error }) {
    let posts;
    try {
      posts = await $content("news").fetch();
    } catch (e) {
      error({ message: "No new or events found" });
    }
    return { posts };
  },

  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toDateString() || ''
    }
  },

  head() {
    const title = 'News and Updates - ' + SITE_INFO.sitename;
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
