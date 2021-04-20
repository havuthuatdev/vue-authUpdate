<template>
  <div>
    <h1>register</h1>
    <form v-on:submit.prevent="handleSubmitRegister">
      <div class="form-row">
        <div class="form-group col-md-6">
          <label for="inputEmail4">Email</label>
          <input
            type="email"
            class="form-control"
            id="inputEmail4"
            placeholder="Email"
            v-model="form.email"
          />
        </div>
        <div class="form-group col-md-6">
          <label for="inputPassword4">Password</label>
          <input
            type="password"
            class="form-control"
            id="inputPassword4"
            placeholder="Password"
            v-model="form.password"
          />
        </div>
      </div>
      <div class="form-group">
        <label for="inputUsername">Username</label>
        <input
          type="text"
          class="form-control"
          id="Username"
          placeholder="Username"
          v-model="form.username"
        />
      </div>
      <button class="btn btn-primary">Sign in</button>
    </form>
  </div>
</template>

<script>
// import {ApiService} from './../services/api.service';

import axios from "axios";
export default {
  name: "register",
  data() {
    return {
      form: {
        email: "",
        password: "",
        username: "",
      },
    };
  },
  methods: {
    handleSubmitRegister: function () {
      console.log("submit thanh cong");
      //   console.log(data)
      axios
        .post("users", {
          user: this.form,
        })
        .then((response) => {
          console.log({response});
          debugger;

          this.$router.push("/dangnhap");
        })
        .catch((err) => {
          console.log("Vui lòng nhập đầy đủ thông tin");
        });
      //
    },
  },
};
</script>