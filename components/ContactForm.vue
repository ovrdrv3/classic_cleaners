<template>
  <div class="py-3">
    <b-form @input="validateForm"
            @change="validateForm"
            name="contact-us"
            ref="form"
            method="POST"
            netlify-honeypot="prefix"
            data-netlify="true">
      <b-form-group v-show="false" label="Prefix:"
                    label-for="prefix">
        <b-form-input id="prefix"
                      name="prefix">
        </b-form-input>
      </b-form-group>
      <b-form-group label="Name:"
                    label-for="Name"
                    :invalid-feedback="errors.name">
        <b-form-input id="name"
                      name="name"
                      type="text"
                      v-model="form.name"
                      placeholder="Name"
                      :state="stateOfElement('name')">
        </b-form-input>

      </b-form-group>
      <b-form-group label="Number:"
                    label-for="Phone Number"
                    :invalid-feedback="errors.phone">
        <b-form-input id="phone"
                      name="phone"
                      type="tel"
                      v-model="form.phone"
                      placeholder="Phone"
                      :state="stateOfElement('phone')">
        </b-form-input>
      </b-form-group>
      <b-form-group label="Email:"
                    label-for="email"
                    :invalid-feedback="errors.email">
        <b-form-input id="email"
                      name="email"
                      type="email"
                      v-model="form.email"
                      placeholder="Email"
                      :state="stateOfElement('email')">
        </b-form-input>
      </b-form-group>
      <b-form-group id="formComment"
                    label="Message:"
                    label-for="comment"
                    :invalid-feedback="errors.comment">
        <b-form-textarea id="comment"
                      name="comment"
                      type="text"
                      v-model="form.comment"
                      :rows="3"
                      :max-rows="6"
                      :state="stateOfElement('comment')">
        </b-form-textarea>
      </b-form-group>
      <b-button type="button" :disabled="errors.any || submissionSuccess" @click.prevent="onSubmit"
 :variant="submitButtonVariant">{{form.submitText}}</b-button>
    </b-form>
  </div>
</template>

<script>

export default {
  data () {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        comment: '',
        submitText: 'Submit'
      },
      submissionAttempt : false,
      submissionSuccess: false,
      submitButtonVariant: 'outline-primary',
      errors: {
        any: false,
        name: '',
        email: '',
        phone: '',
        comment: ''
      }
    }
  },
  methods: {
    encode(data) {
      return Object.keys(data)
        .map(
          key => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`
        )
        .join("&");
    },
    validateForm: function(){
      if (!this.submissionAttempt) { return; }
      this.errors.any = false;
      this.errors.name = '';
      this.errors.email = '';
      this.errors.phone = '';
      this.errors.comment = '';

      if (!this.form.name) {
        this.errors.any = true;
        this.errors.name ='Name required';
      }

      if (!this.form.phone) {
        this.errors.any = true;
        this.errors.phone ='Phone required';
      }

      if (!this.form.email) {
        this.errors.any = true;
        this.errors.email = 'Email required';
      } else if (!this.validEmail(this.form.email)) {
        this.errors.any = true;
        this.errors.email = 'Valid email required';
      }

      if (!this.form.comment) {
        this.errors.any = true;
        this.errors.comment ='Message required';
      }

      if (this.errors.any) {
        this.form.submitText = 'Please check above for errors';
      } else {
        this.form.submitText = 'Submit';
      }

      return this.errors.any;

    },
    stateOfElement(element) {
      if (!this.submissionAttempt) return null;
      return this.errors[element] ? false : true;
    },
    onSubmit () {
      this.submissionAttempt = true;
      var notReadyToProceed = this.validateForm();
      if (notReadyToProceed) {
        return;
      } else {

        fetch("/contact-us", {
          method: "POST",
          headers: { "Content-Type": "application/x-www-form-urlencoded" },
          body: this.encode({
            "form-name": "contact-us",
            ...this.form
          })
        })
          .then(() => {
            this.form.submitText = 'Thanks! You will hear from us shortly!';
            this.submitButtonVariant = 'btn-outline-success';
            this.submissionSuccess = true;
          })
          .catch(() => {
            this.form.submitText = 'Please Refresh Your Page or Try a Different Browser - Error Sending Form';
          });

      }
    },
    validEmail: function (email) {
      var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    }
  }
}
</script>
