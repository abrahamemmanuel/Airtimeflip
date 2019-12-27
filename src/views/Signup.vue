<template>
  <div class="signup">
    <v-toolbar flat>
      <v-toolbar-title>
          <img src="../assets/img/airtimefllip-w.png" alt="airtimeflip-logo">
      </v-toolbar-title>
    </v-toolbar>

    <div class="">
      <v-container fluid>
        <v-row>
          <v-col sm="12" md="6" lg="6">
            <h2>Signup</h2>
            <span>Enter your details below</span>

            <v-snackbar
              v-model="snackbar"
              absolute
              top
              right
              color="success"
            >
              <span>Registration successful!</span>
              <v-icon dark>mdi-checkbox-marked-circle</v-icon>
            </v-snackbar>
            <v-form ref="form" @submit.prevent="submit">
              <v-container fluid>
                <v-row>
                  <v-col cols="12">
                    <v-text-field
                      v-model="form.username"
                      :rules="rules.name"
                      label="Full Name"
                      outlined
                      append-icon="mdi-account"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      outlined
                      v-model="form.email"
                      :rules="[rules.required, rules.email]"
                      label="Email"
                      append-icon="mdi-email"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field 
                      v-model="form.value" 
                      v-mask="mask" 
                      label="Mobile Number"
                      :rules="[rules.required]"
                      outlined
                      append-icon="mdi-phone"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      outlined
                      v-model="password"
                      :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                      :rules="[rules.required, rules.min]"
                      :type="show1 ? 'text' : 'password'"
                      name="input-10-1"
                      label="Password"
                      hint="At least 8 characters"
                      counter
                      @click:append="show1 = !show1"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      outlined
                      v-model="password"
                      :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
                      :rules="[rules.required, rules.min]"
                      :type="show2 ? 'text' : 'password'"
                      name="input-10-1"
                      label="Confirm Password"
                      hint="At least 8 characters"
                      counter
                      @click:append="show2 = !show2"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-checkbox
                      v-model="form.terms"
                      color="green"
                    >
                      <template v-slot:label>
                        <div @click.stop="">
                          Do you accept the
                          <a href="javascript:;" @click.stop="terms = true">terms</a>
                          and
                          <a href="javascript:;" @click.stop="conditions = true">conditions?</a>
                        </div>
                      </template>
                    </v-checkbox>
                  </v-col>
                </v-row>
              </v-container>
              <v-card-actions>
                <v-btn
                  :disabled="!formIsValid"
                  type="submit"
                >Register</v-btn>
              </v-card-actions>
            </v-form>
            <v-dialog v-model="terms" width="70%">
              <v-card>
                <v-card-title class="title">Terms</v-card-title>
                <v-card-text v-for="n in 5" :key="n">
                  {{ content }}
                </v-card-text>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    text
                    color="purple"
                    @click="terms = false"
                  >Ok</v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
            <v-dialog v-model="conditions" width="70%">
              <v-card>
                <v-card-title class="title">Conditions</v-card-title>
                <v-card-text v-for="n in 5" :key="n">
                  {{ content }}
                </v-card-text>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    text
                    color="purple"
                    @click="conditions = false"
                  >Ok</v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
            
          </v-col>
          <v-col sm="12" md="6" lg="6"></v-col>
        </v-row>
      </v-container>
    </div>

    <v-footer
      padless
      absolute
    >
      <v-card
        flat
        tile
        class="text-center"
        width="100%"
      >

        <v-card-text>
          <span>Copyright airtimeflip &#169;</span> {{ new Date().getFullYear() }} — <span>All rights reserved</span>
        </v-card-text>
      </v-card>
    </v-footer>
  </div>
</template>

<!--<script>
  export default {
    data () {

      return {
        username: '',
        email: '',
        value: '',
        show1: false,
        show2: false,
        password: '',

        rules: {
          name: val => (val || '').length > 0 || 'This field is required',
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          email: value => {
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            return pattern.test(value) || 'Invalid e-mail.'
          },

          conditions: false,
          content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris massa. Vestibulum lacinia arcu eget nulla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Curabitur sodales ligula in libero. Sed dignissim lacinia nunc.`,
          terms: false,
          defaultForm,
        },
      }
    },
  }
</script>-->

<script>
  export default {
    data () {
      const defaultForm = Object.freeze({
        username: '',
        email: '',
        value: '',
        show1: false,
        show2: false,
        password: '',
        terms: false,
      })

      return {
        form: Object.assign({}, defaultForm),
        rules: {
          username: [val => (val || '').length > 0 || 'This field is required'],
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          email: value => {
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            return pattern.test(value) || 'Invalid e-mail.'
          },
        },
        conditions: false,
        content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet. Duis sagittis ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta. Mauris massa. Vestibulum lacinia arcu eget nulla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Curabitur sodales ligula in libero. Sed dignissim lacinia nunc.`,
        snackbar: false,
        terms: false,
        defaultForm,
      }
    },

    computed: {
      formIsValid () {
        return (
          this.form.username &&
          this.form.email &&
          this.form.terms
        )
      },
    },

    methods: {
      submit () {
        this.snackbar = true
        this.resetForm()
      },
    },
  }
</script>