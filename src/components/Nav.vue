<script setup>
import { RouterLink } from "vue-router";
import Container from "./Container.vue";
import { ref } from "vue";
import Modal from "../components/AuthModal.vue";

const searchUserName = ref("");

const onSearch = () => {
  return console.log("Onsearch");
};
</script>
<template>
  <div>
    <h1>Nav</h1>
    <ALayoutHeader>
      <Container>
        <div class="nav-container">
          <div class="left-content">
            <RouterLink to="/">Instagram</RouterLink>
            <AInputSearch
              v-model:value="searchUserName"
              placeholder="username..."
              style="width: 200px"
              @search="onSearch"
            />
          </div>

          <div class="right-content">
            <AButton type="primary">Signup</AButton>
            <AButton type="primary">Login</AButton>
          </div>
        </div>
      </Container>
    </ALayoutHeader>
    <Modal />
  </div>
</template>
<style scoped>
.nav-container {
  display: flex;
  justify-content: space-between;
  padding: 0 1rem 0 1rem;
}
.right-content {
}
.left-content {
  display: flex;
  align-items: center;
}
.left-content a {
  margin-right: 1rem;
}
.right-content button {
  margin-left: 1rem;
}
</style>
