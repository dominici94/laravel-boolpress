<template>
  <main class="main">
    <router-view :key="$route.path"></router-view>
    <!-- <div class="posts-container">
      <div class="title">
        <h2>Lista Posts</h2>
      </div>
      <ul>
        <li v-for="post in posts" :key="post.id">
          <a href="#"
            ><h3>{{ post.title }}</h3></a
          >
          <a href="#"
            ><p>{{ post.content }}</p></a
          >
        </li>
      </ul>
    </div> -->
  </main>
</template>

<script>
export default {
  name: "Main",
  // data() {
  //   return {
  //     posts: [],
  //   };
  // },
  // created() {
  //   axios.get("/api/posts").then((response) => {
  //     this.posts = response.data;
  //   });
  // },
};
</script>

<style scoped lang="scss">
main {
  background-color: rgb(245, 245, 245);
  color: rgb(117, 72, 224);
  padding: 70px;
}
.posts-container {
  background-color: rgb(240, 248, 250);
  border-radius: 20px;
  border: 2px solid rgb(50, 190, 230);
  max-width: 1180px;
  margin: auto;
  -webkit-box-shadow: 5px 5px 25px 5px rgba(0, 0, 0, 0.3);
  box-shadow: 5px 5px 25px 2px rgba(0, 0, 0, 0.3);

  .title {
    text-align: center;
    text-transform: uppercase;
    padding: 30px;
    border-bottom: 2px solid rgb(50, 190, 230);

    h2 {
      width: 20%;
      margin: auto;
      background-color: rgb(115, 255, 255);
      border-radius: 10px;
      border: 2px solid rgb(117, 72, 224);
      padding: 5px 0;
    }
  }

  ul {
    list-style: none;

    li {
      padding: 20px 0;
      margin-left: 50px;

      a {
        text-decoration: none;
      }

      h3 {
        text-transform: uppercase;
        padding-bottom: 10px;
        color: rgb(170, 60, 225);
      }
    }

    li:not(:last-child) {
      border-bottom: 2px solid rgb(50, 190, 230);
    }
  }
}
</style>