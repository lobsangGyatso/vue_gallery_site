<template>
    <v-navigation-drawer
    v-model="drawer"
    app
    dark
    temporary
    >
   <v-list>
        <v-list-item v-for="link in links" :key="link.text" router :to="link.routes" active-class="Border">
          <v-list-item-action>
            <v-icon>{{link.icon}}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{link.text}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
</template>

<script>
import { mapGetters, mapMutations } from 'vuex'

export default {
  name: 'CoreDrawer',
  data () {
    return {
      links: [
        { icon: 'fas fa-briefcase', text: 'profile', routes: '/pages/user' },
        { icon: 'fas fa-briefcase', text: 'iphone', routes: '/pages/iphone' }
      ]
    }
  },
  computed: {
    ...mapGetters(['links']),
    drawer: {
      get () {
        return this.$store.state.drawer
      },
      set (val) {
        this.setDrawer(val)
      }
    }
  },
  methods: {
    ...mapMutations(['setDrawer']),
    onClick (e, item) {
      e.stopPropagation()

      if (item.to === '/') {
        this.$vuetify.goTo(0)
        this.setDrawer(false)
        return
      }

      if (item.to || !item.href) return

      this.$vuetify.goTo(item.href)
      this.setDrawer(false)
    }
  }
}
</script>
