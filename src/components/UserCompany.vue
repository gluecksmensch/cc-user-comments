<template>
  <ul>
    <li>{{ name }}</li>
    <li>catchPhrase: {{ catchPhrase }}</li>
    <li>bs: {{ bs }}</li>
  </ul>
</template>

<script>
export default {
  name: "UserCompany",
  props: {
    name: {
      type: String,
      default: ""
    },
    catchPhrase: {
      type: String,
      default: ""
    },
    bs: {
      type: String,
      default: ""
    }
  }
};
</script>
