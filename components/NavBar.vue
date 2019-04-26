<template>
    <b-navbar type="dark" id="navBar" sticky toggleable="md">

    <b-navbar-brand to="/" @click.native="navItemsVisible = false">
      <h1 id="brandText" >Classic Cleaners</h1>
    </b-navbar-brand>

    <b-navbar-toggle target="nav_collapse" class="float-right"></b-navbar-toggle>
    <b-collapse is-nav id="nav_collapse">

      <b-navbar-nav class="ml-auto">
        <b-nav-item href="tel:+18056540117">Call</b-nav-item>
        <b-nav-item to="/about-us">About Us</b-nav-item>
        <b-nav-item to="/contact-us">Contact Us</b-nav-item>
      </b-navbar-nav>

    </b-collapse>
  </b-navbar>
</template>

<style>
#navBar{
  background-color: #00023B;
}

#brandText{
  font-family: 'Fascinate Inline', cursive;
  font-size: 60px;
  color: white;
  text-shadow: 2px 2px 5px #E8DE5B;

}

.nav-link{
  color: white !important;
  font-size: 1.25em;
}

</style>

<script>




</script>
