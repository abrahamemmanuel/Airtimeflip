<template>
  <div class="signin">
    <v-toolbar flat>
      <v-toolbar-title>
          <img src="../assets/img/airtimefllip-w.png" alt="airtimeflip-logo">
      </v-toolbar-title>
    </v-toolbar>

    <div class="">
      <v-container fluid>
        <v-row>
          <v-col sm="12" md="6" lg="6">
            <h2>Sign in</h2>
            <span>Enter your details below</span>

            <v-form>
              <v-container fluid>
                <v-row>
                  <v-col cols="12">
                    <v-text-field
                      outlined
                      v-model="email"
                      :rules="[rules.required, rules.email]"
                      label="Email"
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
                    <v-btn class="mr-4" @click="submit">Login</v-btn>
                  </v-col>
                </v-row>
              </v-container>
            </v-form>
            
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

<script>
  export default {
    data () {
      return {
        email: '',
        show1: false,
        password: '',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          email: value => {
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            return pattern.test(value) || 'Invalid e-mail.'
          },
        },
      }
    },
  }
</script>