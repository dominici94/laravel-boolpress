<template>
  <div>
    <h1>{{ post.title }}</h1>
    <img :src="`/storage/${post.image}`" :alt="post.title" />
    <p>{{ post.content }}</p>
  </div>
</template>

<script>
export default {
  name: "SinglePost",
  data() {
    return {
      post: {},
    };
  },
  created() {
    axios
      .get(`/api/posts/${this.$route.params.slug}`)
      .then((response) => {
        this.post = response.data;
        // dd(response.data);
      })
      .catch(() => {
        // console.log("post not found");
        this.$router.push({ name: "page-404" });
      });
  },
};
</script>

<style>
</style>