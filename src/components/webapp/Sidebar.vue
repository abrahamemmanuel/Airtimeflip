<template>
  <v-card>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant.sync="mini"
      permanent
      app
    >
      <v-list-item v-for="profile in profiles" :key="profile.avatar">
        <v-list-item-avatar>
          <v-img :src="profile.avatar"></v-img>
        </v-list-item-avatar>

        <v-list-item-title class="pt-4"> {{ profile.name }}</v-list-item-title>

        <v-btn
          icon
          @click.stop="mini = !mini"
        >
          <v-icon>mdi-arrow-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-list class="mt-5 pt-5">
        <v-list-item
          v-for="link in links"
          :key="link.title"
          router :to="link.route"
        >
          <v-list-item-icon>
            <v-icon>{{ link.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ link.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      
    </v-navigation-drawer>
  </v-card>
</template>


<script>
  export default {
    data () {
      return {
        drawer: true,
        profiles:[
          { avatar: 'https://randomuser.me/api/portraits/men/85.jpg', name: 'John Leider', position: 'cooperative head'}
        ],
        links: [
          { title: 'Dashboard', icon: 'mdi-view-dashboard-outline', route: '/dashboard' },
          { title: 'Convert-Airtime', icon: 'mdi-cached', route: '' },
          { title: 'Wallet', icon: 'mdi-wallet', route: '' },
          { title: 'Withdrawal', icon: 'mdi-cash-multiple', route: ''},
          { title: 'Transfer', icon: 'mdi-account-convert', route: '' },
          { title: 'Airtime Topup', icon: 'mdi-cellphone-android', route: '' },
          { title: 'Buy Data', icon: 'mdi-access-point-network', route: ''},
          { title: 'Pay Bills', icon: 'mdi-shopping', route: '' },
          { title: 'History', icon: 'mdi-history', route: '' },
          { title: 'Settings', icon: 'mdi-settings-outline', route: '' },
        ],
        mini: false,
      }
    },
  }
</script>

<style scoped>



</style>
