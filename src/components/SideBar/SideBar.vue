<template>
  <aside :class="`${is_expanded ? 'is-expanded' : ''}`">
    <div class="logo">
      <img :src="logoURL" alt="Vue" />
      <span class="titleWeb">T<span class="text-dark">BookStore</span></span>
    </div>

    <div class="menu-toggle-wrap">
      <button class="menu-toggle" @click="ToggleMenu">
        <span class="material-icons"
          ><i class="fa-solid fa-angles-right fa-xs"></i
        ></span>
      </button>
    </div>

    <h3>Menu</h3>
    <div class="menu">
      <router-link to="/" class="button">
        <span class="material-icons"
          ><i class="fa-solid fa-house icon"></i
        ></span>
        <span class="text">Trang chủ</span>
      </router-link>
      <router-link to="/about" class="button">
        <span class="material-icons"><i class="fa-solid fa-book"></i></span>
        <span class="text">Sách</span>
      </router-link>
      <router-link to="/order" class="button">
        <span class="material-icons"
          ><i class="fa-solid fa-bookmark icon"></i
        ></span>
        <span class="text">Đặt hàng</span>
      </router-link>
      <router-link v-if="isLogin" to="/profile" class="button">
        <span class="material-icons"><i class="fa-solid fa-user"></i></span>
        <span class="text">Hồ sơ</span>
      </router-link>
      <router-link v-else to="/login" class="button">
        <span class="material-icons"><i class="fa-solid fa-user"></i></span>
        <span class="text">Profile</span>
      </router-link>
    </div>
    <div class="flex"></div>
    <div class="menu" @click="showModal">
      <div class="button">
        <span class="material-icons"
          ><i class="fa-solid fa-right-from-bracket"></i
        ></span>
        <span class="text">Đăng xuất</span>
      </div>
      <a-modal
        title="Đăng xuất"
        :open="isModal"
        @ok="handleOk"
        @cancel="handleCancel"
        :ok-button-props="okButtonProps"
        okText="Đăng xuất"
        cancelText="Hủy"
      >
        <p>Bạn có chắc muốn đăng xuất khỏi hệ thống?</p>
      </a-modal>
    </div>
  </aside>
</template>

<script setup>
import { ref } from "vue";
import logoURL from "../../assets/logo2.jpg";
import { Button } from "ant-design-vue";
import { useRouter } from "vue-router";

const router = useRouter();

const isLogin = localStorage.getItem("isLoginDG");
const is_expanded = ref(localStorage.getItem("is_expanded") === "true");

const ToggleMenu = () => {
  is_expanded.value = !is_expanded.value;
  localStorage.setItem("is_expanded", is_expanded.value);
};

// Modal andt vue
const isModal = ref(false);

const okButtonProps = {
  style: {
    background: "red", // Đặt màu đỏ cho nút "OK"
  },
};

const showModal = () => {
  isModal.value = true;
};

const handleOk = () => {
  localStorage.removeItem("ID_DG");
  localStorage.removeItem("TenDG");
  localStorage.removeItem("AvatarDG");
  localStorage.removeItem("DiaChiDG");
  localStorage.removeItem("NgaySinhDG");
  localStorage.removeItem("DienThoaiDG");
  localStorage.removeItem("isLoginDG");
  isModal.value = false;
  router.push("/login");
};

const handleCancel = () => {
  isModal.value = false;
};
</script>

<style lang="scss" scoped>
@import "SideBar.scss";
</style>
