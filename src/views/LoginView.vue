//Login.vue
<template>
  <div class="container">
    <div class="row justify-content-md-center">
      <div class="col-md-4">
        <div class="card">
          <div class="card-header">Login</div>
          <div class="card-body">
            <h1>Login</h1>
            <div class="form-group">
              <label for="email">Email address</label>
              <input
                type="string"
                class="form-control"
                placeholder="Username"
                v-model="username"
              />
            </div>
            <div class="form-group">
              <label for="email">Password</label>
              <input
                type="password"
                class="form-control"
                placeholder="Password"
                v-model="password"
              />
            </div>
            <div v-if="error">
              {{ error }}
            </div>
            <div v-if="success" id="success">Logged in Successfully</div>
            <button class="btn btn-primary" @submit="login()">Login</button>
            <hr />
            New user
            <button class="btn btn-success" @click="register()">
              Register
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      password: "",
      username: "",
    };
  },
  methods: {
    async login() {
      const auth = { username: this.username, password: this.password };

      try {
        const res = await axios
          .post("http://159.223.57.121:8080/auth/do-login", { auth })
          .then((res) => res.data);
      } catch (error) {}
    },
  },
};
</script>

<style>
.container {
  padding: 50px;
}
.form-group {
  padding: 0px 10px 8px;
}
.btn {
  margin: 0 10px;
}
.modal-footer p {
  padding: 0px 6px;
}
</style>

