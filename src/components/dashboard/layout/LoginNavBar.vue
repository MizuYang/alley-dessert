<template>
  <nav class="navbar navbar-expand-lg navbar-secondary fixed-top">
    <div class="container">
      <router-link class="navbar-brand logo" title="首頁" to="/"
        ><img
          src="https://github.com/MizuYang/hexschool-Vue-week8/blob/main/src/assets/imageUrl/%E5%B0%88%E6%A1%88%E5%9C%96%E7%89%87/LOGO/%E6%A9%AB%E5%90%91LOGO.png?raw=true"
          alt="小巷弄甜點的logo"
          width="130"
        />
        <h1 class="title">小巷弄甜點_alley_dessert</h1></router-link
      >
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon">
          <i class="bi bi-justify text-primary fs-1"></i>
        </span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul
          class="
            navbar-nav
            ms-auto
            mb-2 mb-lg-0
            align-items-lg-center
            text-center
          "
        >
          <li class="nav-item">
            <router-link
              to="/"
              class="nav-link me-4"
            >
              <i class="bi bi-house-door"></i>
              主頁</router-link
            >
          </li>
          <li class="nav-item me-4">
            <router-link
              to="/products"
              class="nav-link"
              >產品列表</router-link
            >
          </li>
          <li class="nav-item me-4">
            <router-link
              to="/questions"
              class="nav-link"
              >常見問題</router-link
            >
          </li>
          <li class="nav-item me-4">
            <router-link
              to="/about"
              class="nav-link"
              >關於我們</router-link
            >
          </li>
          <li class="nav-item me-4">
            <router-link
              to="/contact"
              class="nav-link"
              >聯絡我們</router-link
            >
          </li>
          <li class="nav-item me-4">
            <router-link
              to="/query_order"
              class="nav-link"
              >查詢訂單</router-link
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "@/assets/stylesheets/helpers/dashboard/login/LoginNavBar.scss";
</style>
