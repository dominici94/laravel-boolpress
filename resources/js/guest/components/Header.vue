<template>
  <header>
    <div class="left-header">
      <a href="/admin/home" class="link">Area riservata</a>
    </div>

    <div class="right-header">
      <nav>
        <ul>
          <li>
            <router-link class="link" :to="{ name: 'home' }">Home</router-link>
          </li>
          <li>
            <router-link class="link" :to="{ name: 'about' }"
              >Chi siamo</router-link
            >
          </li>
          <li>
            <router-link class="link" :to="{ name: 'categories' }"
              >Categorie</router-link
            >
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 20px;
  background-color: #32bee6;
  -webkit-box-shadow: 0px 0px 10px 5px rgba(0, 0, 0, 0.3);
  box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.3);
  position: fixed;
  border-bottom: 1px solid #aa3ce1;

  ul {
    list-style: none;
    display: flex;
    justify-content: space-around;

    li {
      margin-left: 20px;
    }
  }

  .link {
    color: #aa3ce1;
    text-decoration: none;
    text-transform: uppercase;
    font-weight: bold;
    background-color: #73ffff;
    padding: 5px 25px;
    border-radius: 15px;
    -webkit-box-shadow: 0px 5px 20px 5px rgba(17, 103, 231, 0.322);
    box-shadow: 0px 5px 20px 2px rgba(17, 103, 231, 0.322);
  }
}
</style>