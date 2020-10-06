<template>
  <div class="nav-container">
    <b-navbar class="nav" toggleable="lg" type="dark">
      <b-navbar-brand href="#"
        ><img src="@/assets/BuzzRx-Logo.svg" alt="logo"
      /></b-navbar-brand>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-dropdown-item href="#">HOW IT WORKS </b-dropdown-item>
          <b-dropdown-item href="#">GET A CARD</b-dropdown-item>
          <b-dropdown-item href="#"
            >GIVING BACK
            <img src="@/assets/arrow.svg" alt="arrow" />
          </b-dropdown-item>
          <b-dropdown-item href="#"
            >MORE
            <img src="@/assets/arrow.svg" alt="arrow" />
          </b-dropdown-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style lang="scss">
.nav-container {
  width: 1325px;
  margin-left: auto;
  margin-right: auto;
  .nav {
    padding: 10px 80px !important;
    .dropdown-item {
      font-family: "lato", sans-serif !important;
      font-weight: bold;
      font-size: 16px;
    }
    .dropdown-item:focus {
      color: #000 !important;
      background: none !important;
    }
    .dropdown-item:hover {
      color: #b33cc8 !important;
      background: none !important;
    }
  }
}
</style>
