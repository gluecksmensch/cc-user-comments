<template>
  <section class="user">
    <dl>
      <dt>id</dt>
      <dd>{{ id }}</dd>
      <dt>name</dt>
      <dd>{{ name }}</dd>
      <dt>username</dt>
      <dd>{{ username }}</dd>
      <dt>email</dt>
      <dd>{{ email }}</dd>
      <dt>address</dt>
      <dd><UserAddress v-bind="address" /></dd>
      <dt>phone</dt>
      <dd>{{ phone }}</dd>
      <dt>website</dt>
      <dd>{{ website }}</dd>
      <dt>company</dt>
      <dd><UserCompany v-bind="company" /></dd>
    </dl>
  </section>
</template>

<script>
import UserAddress from "./UserAddress";
import UserCompany from "./UserCompany";

export default {
  name: "User",
  components: {
    UserAddress,
    UserCompany
  },
  props: {
    id: {
      type: Number,
      default: null
    },
    name: {
      type: String,
      default: ""
    },
    username: {
      type: String,
      default: ""
    },
    email: {
      type: String,
      default: ""
    },
    address: {
      type: Object,
      default: null
    },
    phone: {
      type: String,
      default: ""
    },
    website: {
      type: String,
      default: ""
    },
    company: {
      type: Object,
      default: null
    }
  }
};
</script>
