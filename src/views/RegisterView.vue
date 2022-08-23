//Register.vue
<template>
  <div class="container">
    <div class="row justify-content-md-center">
      <div class="col-md-4">
        <div class="card">
          <div class="card-header">Register</div>
          <div class="card-body">
            <form>
              <div class="form-group">
                <label for="name">Username</label>
                <input
                  type="text"
                  class="form-control"
                  placeholder="Name.."
                  v-model="username"
                />
              </div>
              <div class="form-group">
                <label for="password">Password</label>
                <input
                  type="password"
                  class="form-control"
                  placeholder="Password.."
                  v-model="password"
                />
              </div>
              <div class="form-group">
                <label for="pfname">Profilename</label>
                <input
                  type="text"
                  class="form-control"
                  placeholder="PrfName.."
                  v-model="pfname"
                />
              </div>
              <div class="form-group">
                <label for="address">Address</label>
                <textarea
                  class="form-control"
                  name="address"
                  placeholder="address"
                  v-model="address"
                ></textarea>
              </div>
              <button type="submit" class="btn btn-primary">Sign Up</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import DataService from "../views/DataService";
export default {
  name: "register",
  data() {
    return {
      tutorial: {
        id: null,
        username: "",
        password: "",
        pfname: "",
        address: "",
        published: false,
      },
      submitted: false,
    };
  },
  methods: {
    Save() {
      var data = {
        username: this.username,
        password: this.password,
        pfname: this.pfname,
        address: this.address,
      };
      DataService.create(data)
        .then((response) => {
          this.tutorial.id = response.data.id;
          console.log(response.data);
          this.submitted = true;
        })
        .catch((e) => {
          console.log(e);
        });
    },

    newTutorial() {
      this.submitted = false;
      this.tutorial = {};
    },
  },
};
</script>

<style>
div .container {
  padding: 50px;
}
</style>
