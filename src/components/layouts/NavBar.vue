<template>
  <nav class="navbar navbar-expand-lg navbar-light fixed-top bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="/">
        <img
          :src="require('@/assets/img/logo.png')"
          alt="Sante Pro"
          class="logo"
        />
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0"></ul>
        <div>
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <i class="fa-solid fa-bell"></i>
              <div class="notification">
                <b-badge
                  variant="light"
                  style="background-color: red; color: white"
                  >4</b-badge
                >
              </div>
            </li>
            <li class="nav-item">
              <i class="fa-solid fa-table-cells-large"></i>
            </li>
            <li class="nav-item">
              <i class="fa-solid fa-user"></i>
            </li>
            <li class="nav-item">
              user name
              <span>
                <i class="fa-solid fa-chevron-down"></i>
              </span>
            </li>
            <li class="nav-item">
              <i class="fa-solid fa-right-from-bracket" style="color: red"></i>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
  <nav class="fakenav"></nav>
  <router-view />
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style>
nav {
  margin-bottom: 20px;
}

.fakenav {
  height: 49px;
}

.logo {
  width: 100px;
  margin-top: -10px;
}

.notification {
  margin-top: -40px;
  margin-left: 10px;
  margin-bottom: 0px;
}
.nav-item {
  margin: 10px;
}
</style>
