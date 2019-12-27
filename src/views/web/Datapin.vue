<template>
  <div class="datapin">
    <v-container fluid>
      <v-row>
        <v-col sm="12" md="6" lg="6">
          <h2 class="main_title">{{ title }}</h2>
          <v-card-text>
                <p class="data_text">{{ datatext }}</p>
                <a class="data_link" href="">{{ linktext }}</a>
          </v-card-text>
        </v-col>
        <v-col sm="12" md="6" lg="6">
            <h2>Data PIN</h2>
            <v-form>
              <v-container fluid>
                <v-row>
                  <v-col cols="12">
                    <v-select
                    :items="items"
                    label="Select Network"
                    outlined
                    ></v-select>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                        v-model="datapin"
                        label="Data PIN"
                        outlined
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                        v-model="number"
                        label="Phone Number"
                        outlined
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                      <v-row>
                          <v-col sm="6">
                              <span>Check your data balance *233*1#</span>
                          </v-col>
                          <v-col sm="6">
                              <v-btn class="mr-4" @click="submit">Recharge</v-btn>
                          </v-col>
                      </v-row>
                  </v-col>
                </v-row>
              </v-container>
            </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>

export default {
  data () {
    return {
        title: 'Lorem ipsum dolor sit amet, Data PIN',
        datatext: 'Lorem ipsum dolor sit amet, ipsum pulvinar suscipit, etiam interdum mattis eget nulla, duis ultricies consectetuer tellus justo, vel odio volutpat nec sodales luctus torquent. Sit vitae dolor. Massa wisi tellus pellentesque tortor.',
        linktext: 'Become a merchant',
        items: ['MTN', 'GLO', '9mobile', 'Airtel'],
    }
  },
};
</script>