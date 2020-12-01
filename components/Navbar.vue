<template>
  <nav>
    <b-navbar type="dark" variant="dark">
      <b-navbar-nav>
        <NuxtLink class="nav-link" to="/">
          Inicio
        </NuxtLink>
        <NuxtLink class="nav-link" to="/about">
          Sobre nosotros
        </NuxtLink>

        <b-nav-item-dropdown text="Lang" class="ml-auto">
          <b-dropdown-item href="#">
            EN
          </b-dropdown-item>
          <b-dropdown-item href="#">
            ES
          </b-dropdown-item>
          <b-dropdown-item href="#">
            RU
          </b-dropdown-item>
          <b-dropdown-item href="#">
            FA
          </b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item-dropdown v-if="$auth.loggedIn" text="User">
          <b-dropdown-item href="#">
            Account
          </b-dropdown-item>
          <b-dropdown-item href="#">
            Settings
          </b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-form v-else>
          <NuxtLink class="nav-link" to="/login">
            Login
          </NuxtLink>
          <NuxtLink class="nav-link" to="/register">
            Register
          </NuxtLink>
        </b-nav-form>
      </b-navbar-nav>
    </b-navbar>
  </nav>
</template>

<script>
export default {
  /* eslint-disable */
}
</script>

<style>
.nuxt-link-exact-active {
  color: rgb(0, 200, 0) !important;
}
</style>
