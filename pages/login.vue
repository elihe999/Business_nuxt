<template>
  <div>
    <h2>用户登录</h2>
    <Input v-model="user.username"></Input>
    <Input type="password" v-model="user.password"></Input>
    <i-button type="info" @click="onLogin">登录</i-button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      user: {
        username: "",
        password: ""
      }
    };
  },
  methods: {
    onLogin() {
      this.$store.dispatch("user/login", this.user).then(ok => {
        if (ok) {
          const redirect = this.$route.query.redirect || "/";
          this.$router.push(redirect);
        }
      });
    }
  }
};
</script>