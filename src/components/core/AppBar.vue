<template>
    <v-app-bar
    app
    >
    <v-app-bar-nav-icon
    class="hidden-md-and-up"
    @click="toggleDrawer"
    >
    </v-app-bar-nav-icon >
    <v-container>
        <v-row align="center">
            <v-img :src="require('@/assets/logo.png')"
            class="mr-5"
            width="48"
            height="48"
            max-width="48"
            ></v-img>
            <v-btn  class="hidden-sm-and-down ml-3" text>
                lobangs
            </v-btn>
            <v-spacer />

        <v-text-field
          append-icon="mdi-magnify"
          flat
          hide-details
          solo-inverted
          style="max-width: 300px;"
        />
        </v-row>
    </v-container>
    </v-app-bar>
</template>

<script>
import { mapGetters, mapMutations } from 'vuex'

export default {
  name: 'CoreAppBar',
  computed: {
    ...mapGetters(['links'])
  },

  methods: {
    ...mapMutations(['toggleDrawer']),
    onClick (e, item) {
      e.stopPropagation()
      if (item.to || !item.href) return
      this.$vuetify.goTo(item.href.endsWith('!') ? 0 : item.href)
    }
  }
}
</script>
