<template>
    <b-navbar id="navBar" sticky toggleable="md">

    <b-navbar-brand to="/" @click.native="navItemsVisible = false">
      <h1 id="brandText" >Classic Cleaners</h1>
    </b-navbar-brand>

    <b-navbar-toggle target="nav_collapse" class="float-right"></b-navbar-toggle>
    <b-collapse is-nav id="nav_collapse" v-model="navItemsVisible">

      <b-navbar-nav class="ml-auto">
        <b-nav-item href="tel:+18056540117">Call</b-nav-item>
        <b-nav-item to="/about-us">About Us</b-nav-item>
        <b-nav-item to="/contact-us">Contact Us</b-nav-item>
      </b-navbar-nav>

    </b-collapse>
  </b-navbar>
</template>

<style lang="scss">

#brandText{
  font-family: 'Fascinate Inline', cursive;
  font-size: 60px;
}

</style>

<script>

export default {
  data () {
    return {
      navItemsVisible: false
    }
  },
  methods: {
      handleNavBarVisibility: function (){
        // If the navbar items are not visible we do not want to allow this to show the items, only collapse them.
        if (this.navItemsVisible) {
          this.navItemsVisible = false;
        }
      }
    }
}


</script>
