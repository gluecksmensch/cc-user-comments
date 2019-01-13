<template>
  <div>Geo: {{ lat }}, {{ lng }}</div>
</template>

<script>
export default {
  name: "UserAddressGeo",
  props: {
    lat: {
      type: String,
      default: ""
    },
    lng: {
      type: String,
      default: ""
    }
  }
};
</script>
