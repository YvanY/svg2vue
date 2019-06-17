<script>
import decamelize from 'decamelize'

export default {
  props: {
    width: {
      type: [Number, String],
      default: '1em'
    },

    height: {
      type: [Number, String],
      default: '1em'
    },

    inheritFill: {
      type: Boolean,
      default: true
    }
  },

  computed: {
    iconClass() {
      return ['svg2vue', decamelize(this.$options.name, '-'), { 'svg2vue-inherit-fill': this.inheritFill }]
    },

    iconAttrs() {
      return {
        class: this.iconClass,
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

.svg2vue-inherit-fill {
  fill: currentColor;
}

.svg2vue-inherit-fill path, .svg2vue-inherit-fill g {
  fill: inherit;
}
</style>
