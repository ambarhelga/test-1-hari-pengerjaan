//Navbar.vue
<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <router-link class="navbar-brand" to="/"></router-link>
    <div class="container-fluid">
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarToggleExternalContent"
        aria-controls="navbarToggleExternalContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
    </div>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <router-link class="nav-link" to="/">Login</router-link>
        </li>
      </ul>
      <ul class="navbar-nav">
        <li class="nav-item">
          <router-link class="nav-link" to="/register">Register</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/data">Data</router-link>
        </li>
      </ul>
    </div>
    <nav class="ts-sidebar">
      <ul class="ts-sidebar-menu">
        <li><i class="fa fa-dashboard"></i> Katalog Buku</li>
        <li><i class="fa fa-users"></i> Peminjaman</li>
      </ul>
    </nav>
  </nav>
</template>

<script>
export default {
  name: "app",
};
</script>
 