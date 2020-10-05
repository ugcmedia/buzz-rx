<template>
  <div>
    <b-navbar class="nav" toggleable="lg" type="dark" variant="light">
      <b-navbar-brand href="#"
        ><img src="@/assets/BuzzRx-Logo.svg" alt="logo"
      /></b-navbar-brand>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-dropdown-item href="#">HOW IT WORKS</b-dropdown-item>
          <b-dropdown-item href="#">GET A CARD</b-dropdown-item>
          <b-dropdown-item href="#">GIVING BACK</b-dropdown-item>
          <b-dropdown-item href="#">MORE</b-dropdown-item>
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
.nav {
  padding: 10px 50px !important;
  .dropdown-item{
    font-family: "lato", sans-serif !important;
    font-weight: bold;
    font-size: 16px;
  }
}
</style>
