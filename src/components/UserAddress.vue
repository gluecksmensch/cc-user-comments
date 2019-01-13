<template>
  <div>
    {{ street }}, {{ suite }}, {{ city }}, {{ zipcode }}
    <UserAddressGeo v-bind="geo" />
  </div>
</template>

<script>
import UserAddressGeo from "./UserAddressGeo";

export default {
  name: "UserAddress",
  components: {
    UserAddressGeo
  },
  props: {
    street: {
      type: String,
      default: ""
    },
    suite: {
      type: String,
      default: ""
    },
    city: {
      type: String,
      default: ""
    },
    zipcode: {
      type: String,
      default: ""
    },
    geo: {
      type: Object,
      default: null
    }
  }
};
</script>
