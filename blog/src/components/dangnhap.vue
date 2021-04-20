<template>
  <div class="formlogin">
    <h2>dang nhap</h2>
    <form @submit.prevent="handleSubmitLogin">
      <div class="form-group">
        <label for="exampleInputEmail1">Email address</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          placeholder="Enter email"
          v-model="form.email"
        />
        <small id="emailHelp" class="form-text text-muted"
          >We'll never share your email with anyone else.</small
        >
      </div>
      <div class="form-group">
        <label for="exampleInputPassword1">Password</label>
        <input
          type="password"
          class="form-control"
          id="exampleInputPassword1"
          placeholder="Password"
          v-model="form.password"
        />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "login",
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    handleSubmitLogin: function () {
      // var self = this
      axios.post("users/login", {
          user: this.form
        })
        .then((response) => {
          // console.log(response.data.user.token)
          
          localStorage.setItem('token', response.data.user.token);
          console.log(localStorage.getItem('token'))
          this.$router.push('/home');
          debugger
        })
        .catch((err) => {
          console.log("Đăng nhập không thành công");
        });
    //   localStorage.setItem("token", response.data.token);
      // this.$router.push("/home");
    }
  },
};
</script>
<style scoped>
/* .formlogin {
  width: 50%;
  height: 70%;
  margin: 0px 700px;
} */
</style>