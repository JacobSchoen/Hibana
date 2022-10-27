<template>
  <div class="hello">
    <section>
      <div>
        <h1> Welcome to Hibana Blog</h1>
        <div v-for="post in posts" class="post-item" :key="post._id">
            <router-link :to="`/blog/${post.slug.current}`">
              <h2>{{ post.title }}</h2>
            </router-link>
            <p>{{post.excerpt}}</p>
            <hr />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import sanity from "../client";

const query = `*[_type == "post"]{
  _id,
  title,
  slug,
  excerpt
}[0...50]`;

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return{
      loading: true,
      posts: []
    }
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      this.error = this.post = null;
      this.loading = true;
      sanity.fetch(query).then(
        (posts) => {
          this.loading = false;
          this.posts = posts;
        },
        (error) => {
          this.error = error;
        }
      );
    },
  },
}
</script>

<style scoped>
</style>
