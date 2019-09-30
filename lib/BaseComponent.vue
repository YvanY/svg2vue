<script>
export default {
  props: {
    width: {
      type: [Number, String],
      default: '1em'
    },

    height: {
      type: [Number, String],
      default: '1em'
    }
  },

  computed: {
    iconAttrs() {
      return {
        height: this.height,
        width: this.width
      }
    },

    iconListeners() {
      return this.$listeners
    }
  }
}
</script>

<style>
.svg2vue {
  vertical-align: -0.15em;
}

.svg2vue:not([fill]) {
  fill: currentColor;
}
</style>
