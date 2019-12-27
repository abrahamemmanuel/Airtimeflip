<template>
  <div class="home">
    <v-container fluid>
      <v-row>
        <v-col sm="12" md="6" lg="6">
          <span class="home_title-caption">{{ subtitle }}</span>
          <h1 class="home_title">{{ title }}</h1>
        </v-col>
        <v-col sm="12" md="6" lg="6">
          <img width="100%" :src="image" alt="">
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>

export default {
  data () {
    return {
      subtitle: 'welcome to airtimeflip',
      title: 'we make it easier for you to convert airtime to cash',
      image: require('../../assets/svg/skateboard.svg')
    }
  },
};
</script>