<script>
import menu from '@/api/menu'
import VuePerfectScrollbar from 'vue-perfect-scrollbar'


export default {
  name: 'AppDrawer',
  components: {
    VuePerfectScrollbar
  },
  props: {
    expanded: {
      type: Boolean,
      default: true
    },
    drawWidth: {
      type: [Number, String],
      default: '260'
    },
    showDrawer: Boolean
  },
  data () {
    return {
      mini: false,
      menus: menu,
      scrollSettings: {
        maxScrollbarLength: 160
      }
    }
  },
  computed: {
    computeGroupActive () {
      return true
    },
    computeLogo () {
      return '/static/m.png'
    },

    sideToolbarColor () {
      return this.$vuetify.options.extra.sideNav
    }
  },
  created () {},

  methods: {
    genChildTarget (item, subItem) {
      if (subItem.href) return
      if (subItem.component) {
        return {
          name: subItem.component
        }
      }
      return { name: `${item.group}/${subItem.name}` }
    }
  }
}
</script>

<style lang="stylus" scoped>
.app--drawer
  overflow: hidden
  .drawer-menu--scroll
    height: calc(100vh - 48px)
    overflow: auto
</style>
