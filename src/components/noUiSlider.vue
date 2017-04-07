<template>
  <div>
    <div class="vue-nouislider" :id="sliderId">
    </div>
  </div>
</template>

<script>
  var noUiSlider = require('nouislider')

  export default {
    name: 'nouislider',

    props: {
      config: {
        type: Object,
        required: true,
      },
      values: {
        type: Array,
        required: true,
      },
      id: {
        type: String,
        required: false,
      },
    },

    data () {
      return {
        slider: null,
      }
    },

    methods: {
      /**
       * Update a slider handle value
       * @param value
       * @param handle
       */
      updateValue: function (value, handle) {
        this.$set(this.values, handle, value[handle])
      },
      /**
       * Create a unique slider id
       * @returns {string}
       */
      uniqueId: function () {
        function s4 () {
          return Math.floor((1 + Math.random()) * 0x10000)
            .toString(16)
            .substring(1)
        }
        return 'vue-nouislider-' + s4() + s4()
      },
    },

    computed: {
      /**
       * Set the slider ID with prop value or random ID
       * @returns {string}
       */
      sliderId () {
        if (this.id === undefined) {
          return this.uniqueId()
        }

        return this.id
      },
    },

    mounted () {
      this.slider = document.getElementById(this.sliderId)

      this.config.start = this.values

      noUiSlider.create(this.slider, this.config)

      this.slider.noUiSlider.on('update', this.updateValue)

      // Listen for Event on parent component if values are changed
      this.$parent.$on('updateValue', (value) => {
        this.slider.noUiSlider.set(value)
      })

      // Fire Event if new value is set with the slider
      this.slider.noUiSlider.on('change', (newValues) => {
        this.$parent.$emit('newValueSet', newValues)
      })

      this.slider.noUiSlider.on('start', () => {
        this.$parent.$off('updateValue')
      })

      this.slider.noUiSlider.on('end', () => {
        this.$parent.$on('updateValue', (value) => {
          this.slider.noUiSlider.set(value)
        })
      })
    },
  }
</script>

<style scoped lang="scss">
  @import '~nouislider/distribute/nouislider.min.css';
</style>
