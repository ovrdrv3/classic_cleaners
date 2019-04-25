<template>
  <b-container>
    <div>
      <h1 class="my-5">The best dry cleaning in Ventura County!</h1>
      <b-row class="my-5">
        <b-col sm="4">
          <h1>Our Services</h1>
          <p>We offer many services at a great price. Please <a href="tel:+18056540117">give us a call</a> or <nuxt-link to="/contact-us">contact us here</nuxt-link> for pricing.</p>
        </b-col>
        <b-col sm="8">
          <b-list-group flush>
              <b-list-group-item>Tuxedo Rentals &amp; Sales</b-list-group-item>
              <b-list-group-item>Ladies &amp; Mens Tailoring</b-list-group-item>
              <b-list-group-item>Sewing Custom Made</b-list-group-item>
              <b-list-group-item>Custom Sewing &amp; Alterations</b-list-group-item>
              <b-list-group-item>Dry Cleaning &amp; Laundry</b-list-group-item>
          </b-list-group>
        </b-col>
      </b-row>
      <b-row class="my-5">
        <b-col>
          <h1>Our Hours</h1>
          <p>Monday - Friday</p>
          <p>8AM - 6PM</p>

          <p>Saturday and Sunday</p>
          <p>8AM - 6PM</p>

          <p>We have a 24-hour drop-off service too! (Christina - more info needed on this.)</p>
        </b-col>
      </b-row>
      <b-row class="my-5">
        <b-col sm="4">
          <h1>Our location</h1>
          <p>3875 Telegraph Rd<br>Ventura, CA 93003</p>
          <p> We are located between Mills and Ventura College on Telegraph, right next door to K D Village Donuts</p>
        </b-col>
        <b-col sm="8">
          <div id="map"></div>
        </b-col>
      </b-row>
    </div>
  </b-container>
</template>

<script>

export default {
  mounted(){
    // Initialize and add the google map
    var location = {lat: 34.274220, lng: -119.242679};
    var map = new google.maps.Map(
        document.getElementById('map'), {zoom: 15, center: location});
    var marker = new google.maps.Marker({position: location, map: map});
  }
}
</script>

<style>


#map {
  height: 400px;
  /*width:100%;*/
  background-color: grey;
}

.logo{
  max-height: 300px;
  max-width: 300px;
}

</style>
