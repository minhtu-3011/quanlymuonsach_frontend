<template>
  <nav class="navbar bg-body-tertiary">
    <div
      class="container-fluid"
      style="background-color: aquamarine; height: 50px"
    >
      <div class="infoUser">
        <div v-if="isUserLoggedIn()" class="contentInfo">
          <img :src="imageUser" class="imageUser" alt="noImage" />
          <span class="nameUser">
            {{ username }}
          </span>
        </div>
        <div v-else>
          <router-link to="/login" class="text-decoration-none">
            <button class="btnLogin">Đăng nhập</button>
          </router-link>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
const isUserLoggedIn = () => {
  return localStorage.getItem("isLoginDG") === "true";
};
const username = localStorage.getItem("TenDG");
const avatar = localStorage.getItem("AvatarDG");
const imageUser = `http://localhost:3000/${avatar}`;
</script>

<style lang="scss" scoped>
@import "AppHeader.scss";
</style>
