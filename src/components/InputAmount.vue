<script>
export default {
  name: 'InputAmount',
  props: {
    value: {
      type: String,
      default: null
    },
    currency: {
      type: String,
      default: null
    },
    locale: {
      type: String,
      default: 'fr-FR'
    }
  },
  data () {
    return {
      isInputTarget: false,
      unChangedValue: this.value,
    };
  },
  computed: {
    displayValue: {
      get() {
        if (this.isInputTarget) return this.value?.toString();

        const options = { maximumFractionDigits: 2 };
        if (this.currency) {
          options.style = 'currency';
          options.currency = this.currency;
        }

        return new Intl
          .NumberFormat(this.locale,  options)
          .format(this.formatFloatValue(this.value))
        ;
      },
      set(value) {
        value = this.formatFloatValue(value).replace(/[^\d.]/g, '')
        if (this.isNumber(value)) this.$emit('input', value);
      }
    }
  },
  methods: {
    isNumber(value) {
      return !isNaN(parseFloat(value));
    },
    formatFloatValue(value) {
      return value.replace(',', '.');
    },
    onBlur() {
      this.isInputTarget = false;
      if (!this.displayValue.length) this.displayValue = this.unChangedValue
    }
  }
}
</script>

<template>
  <input
    type="text"
    v-model="displayValue"
    @blur="onBlur"
    @focus="isInputTarget = true"
  />
</template>
