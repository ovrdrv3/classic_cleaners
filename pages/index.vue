<template>
  <b-container>
    <div>
      <h1 class="my-5">The best dry cleaning in Ventura County!</h1>
      <CompanyInfo/>
      <div class="my-5">
        <h1>We pride ourself in the service that we bring to our customers and community. Stop on by!</h1>
        <br>
        <img src="~/assets/images/classic_cleaners_logo.jpg" style="height: 360px; width: 360px;" alt="Classic Cleaners Logo" class=" mx-auto d-block"></img>
      </div>
    </div>
  </b-container>
</template>

<script>

import CompanyInfo from '~/components/CompanyInfo.vue';

export default {
  mounted(){
    // Initialize and add the google map
    var location = {lat: 34.274220, lng: -119.242679};
    var map = new google.maps.Map(
        document.getElementById('map'), {zoom: 15, center: location});
    var marker = new google.maps.Marker({position: location, map: map});
  },
  components: {
      CompanyInfo
  }
}
</script>

<style>


#map {
  height: 400px;
}

.logo{
  max-height: 300px;
  max-width: 300px;
}

</style>
