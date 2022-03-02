<template>
  <div>
    <h1>{{ post.title }}</h1>
    <img :src="`/storage/${post.image}`" :alt="post.title" />
    <p>{{ post.content }}</p>
    <div>
      <h3>Lascia un commento</h3>
      <form @submit.prevent="addComment()">
        <div>
          <input
            type="text"
            id="name"
            placeholder="inserisci il nome"
            v-model="formData.name"
          />
        </div>
        <div>
          <textarea
            id="content"
            cols="60"
            rows="10"
            placeholder="inserisci il testo del commmento"
            v-model="formData.content"
          ></textarea>
          <div v-if="formErrors.content">
            <ul>
              <li v-for="(error, index) in formErrors.content" :key="index">
                {{ error }}
              </li>
            </ul>
          </div>
        </div>
        <div>
          <button type="submit">Aggiungi commento</button>
        </div>
      </form>
    </div>
    <div>
      <h3>Commenti</h3>
      <ul>
        <li v-for="comment in post.comments" :key="comment.id">
          <h4>{{ comment.name }}</h4>
          <p>{{ comment.content }}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "SinglePost",
  data() {
    return {
      post: {},
      formData: {
        name: "",
        content: "",
        post_id: null,
      },
      commentSent: false,
      formErrors: {},
    };
  },
  methods: {
    addComment() {
      axios
        .post("/api/comments", this.formData)
        .then((response) => {
          this.formData.name = "";
          this.formData.content = "";
          this.commentSent = true;
          alert("commento in fase di approvazione");
        })
        .catch((error) => {
          this.formErrors = error.response.data.errors;
        });
    },
  },
  created() {
    axios
      .get(`/api/posts/${this.$route.params.slug}`)
      .then((response) => {
        this.post = response.data;
        this.formData.post_id = this.post.id;
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