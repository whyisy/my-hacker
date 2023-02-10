<template>
  <div class="user_profile2">
      <strong>User name : {{ userInfo.id }}</strong>
      <b>Write : {{ userInfo.created }}</b>
      <b>Karma : {{ userInfo.karma }}</b>
  </div>
</template>

<script>
export default {
  computed: {
      userInfo() {
          return this.$store.state.user;
      }
  },
  created() {
      this.$store.dispatch('FETCH_USER', this.$route.params.id)
  }
}
</script>

<style>
.user_profile2 {font-size: 24px}
.user_profile2 > * {display: block;}
.user_profile2 > span {margin-right:5px}
.user_profile2 > strong {color:#2455c3; }
</style>