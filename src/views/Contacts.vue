<template>
  <div class="contacts">
    <h1 class="body-1 grey--text">Contacts</h1>
    <v-container class="cont">
      <v-card shaped raised>
        <v-card-title>
          <span class="headline">Send a message</span>
        </v-card-title>
        <v-card-text>
          <v-form ref="form" v-model="valid" :lazy-validation="lazy">
            <v-text-field
              v-model="name"
              :rules="nameRules"
              label="Name"
              required
            ></v-text-field>

            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              required
            ></v-text-field>

            <v-textarea
              :rules="textRules"
              label="Message"
              counter
              no-resize
            ></v-textarea>

            <v-checkbox
              v-model="checkbox"
              :rules="[v => !!v || 'You must agree to continue!']"
              label="Do you agree?"
              required
            ></v-checkbox>

            <v-btn
              block
              :disabled="!valid"
              color="success"
              class="mr-4"
              @click="validate"
            >
              Send
            </v-btn>
          </v-form>
        </v-card-text>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    nameRules: [
      v => !!v || "Name is required",
      v => (v && v.length >= 2) || "Name must be more then 2 characters"
    ],
    email: "",
    emailRules: [
      v => !!v || "E-mail is required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
    ],
    textRules: [
      v => !!v || "Message is required",
      v => (v && v.length >= 10) || "Message must be less than 10 characters"
    ],
    checkbox: false,
    lazy: false
  }),

  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.snackbar = true;
      }
    }
  }
};
</script>

<style>
.cont {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>
