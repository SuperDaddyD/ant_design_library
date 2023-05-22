<script setup>
import { defineComponent, ref, defineProps } from "vue";

const { isLogin } = defineProps(["isLogin"]);

const visible = ref(false);
const title = isLogin ? "Login" : "Signup";
const value = ref("");

const showModal = () => {
  visible.value = true;
};

const handleOk = (e) => {
  console.log(e);
  visible.value = false;
};
</script>

<template>
  <div>
    {{ value }}
    <AButton type="primary" @click="showModal">{{ title }}</AButton>
    <AModal
      class="theModal"
      v-model:visible="visible"
      :title="title"
      @ok="handleOk"
    >
      <a-input v-if="!isLogin" v-model:value="value" placeholder="Username" />
      <a-input v-model:value="value" placeholder="Email" />
      <a-input v-model:value="value" placeholder="Password" />
    </AModal>
  </div>
</template>

<style>
.ant-modal-body {
  height: 200px;
}
.ant-modal-body input {
  margin: 10px 0 10px 0;
}
.ant-btn{
  margin-left: 1rem;
}
</style>
