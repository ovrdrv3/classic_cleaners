<template>
  <b-container>
      <div class="my-5">
        <h1>About Classic Cleaners</h1>
        <b-row class="my-5">
          <b-col sm="4">
            <p>Classic Cleaners is family owned and has been in business for over 25 years. We are proud members of the BBB, we at Classic Cleaners take pride in our customers that we serve and in the people we employee. We look forward to reading your comments and reviews on our service.</p>
          </b-col>
          <b-col sm="8">
            <img src="~/assets/images/classic_cleaners_location.jpg" alt="Classic Cleaners Storefront" class="img-fluid mx-auto d-block"></img>
          </b-col>
        </b-row>
        <b-row class="my-5">
          <b-col sm="8">
            <img src="~/assets/images/classic_cleaners_interior.jpg" alt="Classic Cleaners Storefront" class="img-fluid mx-auto d-block"></img>
          </b-col>
          <b-col sm="4">
            <p>We have some exciting and positive changes slowly taking effect, here at Classic Cleaners, we are a green cleaners, echo friendly and we like encourage recycling of the hangers and plastic bags.</p>
          </b-col>
        </b-row>
      </div>
      <CompanyInfo/>
  </b-container>
</template>

<script>

import CompanyInfo from '~/components/CompanyInfo.vue';

export default {
  head () {
    return {
      title: 'Contact Us',
      meta: [
        { hid: 'description', name: 'description', content: 'Classic Cleaners Ventura Dry Cleaning Contact Us Page' }
      ]
    }
  },
  components: {
    CompanyInfo
  }
}
</script>
