<template>
  <div class="contact">
    <v-container fluid>
      <v-row>
        <v-col cols="12">
          <span class="main_title-caption">{{ subtitle}}</span>
          <h2 class="main_title">{{ title }}</h2>
          <img class="line" :src="line">
        </v-col>
      </v-row>
      <v-row>
          <v-col sm="12" md="6" lg="6">
              <h5>Send Us A Message</h5>
              <span>We will get back to you as fast as possible</span>

              <v-form>
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
                  </v-row>
              </v-form>
          </v-col>
          <v-col sm="12" md="6" lg="6"></v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>

export default {
  data () {
    return {
      subtitle: 'Contact Us',
      title: 'If you have any question',
      line: require('../../assets/img/line.png'),
    }
  },
};
</script>