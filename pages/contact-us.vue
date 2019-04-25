<template>
  <b-container>
        <h1 class="my-5">Contact Us - The best dry cleaning in Ventura County!</h1>

        <div class="py-3">
          Feel free to fill out the contact form below if you have any questions!
        </div>
        <div class="py-3">
          Our Number:
          <br>
          <a href="tel:+18056540117">(805) 654-0117</a>
        </div>
        <div class="py-3">
          Our Email:
          <br>
          <a href="mailto:ChristinaHaywood5@gmail.com?subject=Dry%20Cleaning%20Inquiry">ChristinaHaywood5@gmail.com</a>
        </div>
        <no-ssr>
          <ContactForm/>
        </no-ssr>


  </b-container>
</template>

<script>

import ContactForm from '~/components/ContactForm.vue';

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
    ContactForm
  }

}
</script>

<style>

ul{
  text-align: left;
}

li{
  margin-top: 10px;
}

.links {
  padding-top: 15px;
}
</style>
