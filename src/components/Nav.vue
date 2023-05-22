<script setup>
import { RouterLink } from "vue-router";
import Container from "./Container.vue";
import { ref, defineProps } from "vue";
import LoginModal from "../components/AuthModal.vue";

const isLogin = ref(false);
const searchUserName = ref("");

const isAuthenticated = ref(false);

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

          <div v-if="!isAuthenticated" class="left-content authenticated">
            <LoginModal :isLogin="true" />
            <LoginModal :isLogin="isLogin" />
          </div>
          <!-- <AButton type="primary">Login</AButton> -->
          <div v-else class="authenticated">
            <AButton type="primary">Profile</AButton>
            <AButton type="primary">Logout</AButton>
          </div>
        </div>
      </Container>
    </ALayoutHeader>
  </div>
</template>
<style scoped>
.nav-container {
  display: flex;
  justify-content: space-between;
  padding: 0 1rem 0 1rem;
}
.right-content {
  display: flex;
  align-items: center;
  gap: 1rem;
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
.ant-btn{
  margin-left: 1rem;
}
</style>
