<template>
  <div class="about">
    <v-container fluid>
      <v-row>
        <v-col sm="12" md="6" lg="6">
          <span class="main_title-caption">{{ subtitle}}</span>
          <h2 class="main_title">{{ title }}</h2>
          <img class="line" :src="line">
          <v-card-text>
                <p class="about_text">{{ abouttext }}</p>
                <a class="faq_link" :href="faqlink">{{ linktext }}</a>
          </v-card-text>
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
      subtitle: 'hello there',
      title: 'We Are Airtime Flip',
      line: require('../../assets/img/line.png'),
      abouttext: 'AirtimeFlip makes it possible for you to convert airtime to money deposited into your bank account. It boasts as one of the fastest airtime converter in Nigeria with 99% automated transaction.',
      faqlink: '/faq',
      linktext: 'Here are answers to your questions.',
      image: require('../../assets/svg/transfer_money.svg')
    }
  },
};
</script>