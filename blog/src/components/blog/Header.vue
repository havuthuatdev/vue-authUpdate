<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Navbar</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item active">
            <router-link
              to="home"
              class="nav-item nav-link"
              active-class="active"
              exact
            >
              Home
            </router-link>
          </li>
          <li class="nav-item active">
            <router-link
              to="dangnhap"
              class="nav-item nav-link"
              active-class="active"
              exact
            >
              Login
            </router-link>
          </li>
          <li class="nav-item">
            <router-link
              to="register"
              class="nav-item nav-link"
              active-class="active"
              exact
            >
              Register
            </router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Pricing</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="#">Disabled</a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>
<script>
export default {
  name: "login",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
    };
  },
};
</script>