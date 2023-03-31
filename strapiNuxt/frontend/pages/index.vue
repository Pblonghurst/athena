<template>
  <div>
    <Tabs />
  </div>
</template>

<script>
  export default {
    name: 'IndexPage',
    data() {
        return {};
    },
    computed: {
      currentUser() {
        return this.$store.state.user;
      },
    },
    methods: {
      signOut() {
        this.$fire.auth.signOut();
        window.location = "/login";
      },
    },
  }
</script>
