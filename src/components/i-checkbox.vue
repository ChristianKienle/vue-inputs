<template>
<input type="checkbox" :checked="checked" :true-value="true-value"  v-model="valueModel"/>
</template>

<script>
export default {
  name: "i-checkbox",
  props: ["value", "true-value"],
  inheritAttrs: false,
  watch: {
  },
  data() {
    return {
      localValue: true
    };
  },
  methods: {
  },
  computed: {
    checked() {
      if(Array.isArray(this.value)) {
        return this.value.indexOf(this.trueValue) >= 0;
      }
      return this.value === true || this.value === this.trueValue
    },
    valueModel: {
      get() {
        return this.value;
      },
      set(value) {
        console.log('emitting', value);
        this.$emit("input", value);
      }
    },
    listeners() {
      return {};
      return Object.keys(this.$listeners)
        .filter(key => key !== "input")
        .reduce((obj, key) => {
          obj[key] = this.$listeners[key];
          return obj;
        }, {});
    }
  }
};
</script>
