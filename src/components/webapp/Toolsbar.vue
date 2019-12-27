<template>
    <div>
        <v-toolbar flat>
            <v-toolbar-title>
                <span class="manager_number">+234 000 0000 0000</span>
                <v-avatar>
                    <img
                        class="manager_img"
                        src="https://cdn.vuetifyjs.com/images/john.jpg"
                        alt="John"
                    >
                </v-avatar>
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <v-toolbar-items>
                <v-avatar color="red">
                    <span class="white--text headline">CJ</span>
                </v-avatar>
            </v-toolbar-items>

            <template v-if="$vuetify.breakpoint.smAndUp">
                <v-badge
                color="green"
                overlap
                >
                    <template v-slot:badge>
                        <span v-if="messages > 0">{{ messages }}</span>
                    </template>
                    <v-icon large>mdi-bell-outline</v-icon>
                </v-badge>
            </template>
        </v-toolbar>
    </div>
</template>


<script>
export default {

};
</script>

<style scoped>

.manager_number {
    font-size: .8rem;
}

</style>