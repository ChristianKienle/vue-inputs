<template>
<input v-on="listeners" v-model="localValue" @input="input" type="text" />
</template>

<script>
export default {
  name: "i-input",
  props: ['value'],
  watch: {
    value: {
      immediate: true,
      handler(newValue) {
        this.localValue = newValue;
      }
    }
  },
  data: () => {
    return {
      localValue: ''
    };
  },
  methods: {
    input(event) {
      console.log("input", this.localValue)
      this.$emit('input', this.localValue);
    }
  },
  computed: {
    listeners() {
      const {input, ...listeners} = this.$listeners;

      return listeners;
    }
  },
};
</script>
