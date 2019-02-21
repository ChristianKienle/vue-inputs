<template>
  <div class="hello">
    <div class="box">
      <h2>First Name</h2>
      <p>i-input: <i-input v-model="firstName" /></p>
      <p>i-input: <i-input v-model="firstName" /></p>
      <p>input: <input type="text" v-model="firstName" /></p>
      <p>First Name: <strong>{{firstName}}</strong></p>
    </div>

    <br />
    <br />

    <div id="raw-checkboxes" class="box">
      <h2>is male</h2>
      <p>i-checkbox: <i-checkbox v-model="isMale" /></p>
      <p>i-checkbox: <i-checkbox v-model="isMale" /></p>
      <p>input: <input type="checkbox" v-model="isMale" /></p>
      <p>Is Male: <strong>{{isMale}}</strong></p>
    </div>

    <div id="array-checkboxes" class="box">
      <h2>is male</h2>
      <p>i-checkbox value=1: <i-checkbox true-value="1" v-model="checkedNumbers" /></p>
      <p>i-checkbox value=2: <i-checkbox true-value="2" v-model="checkedNumbers" /></p>
      <p>i-checkbox value=3: <i-checkbox true-value="3" v-model="checkedNumbers" /></p>
      <p>i-checkbox value=4: <i-checkbox true-value="4" v-model="checkedNumbers" /></p>
      <p>input value=5: <input type="checkbox" true-value="5" v-model="checkedNumbers" /></p>
      <p>input value=1: <input type="checkbox" true-value="5" v-model="checkedNumbers" /></p>
      <p>checkedNumbers: <strong>{{checkedNumbers}}</strong></p>
    </div>

  </div>
</template>

<script>
import IInput from "./i-input.vue";
import ICheckbox from "./i-checkbox.vue";

export default {
  data: () => ({
    firstName: "chris",
    isMale: true,
    checkedNumbers: ["2"]
  }),
  components: { ICheckbox, IInput },
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box {
  border: 1px solid #efefef;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
