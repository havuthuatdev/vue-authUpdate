<template>
  <div>
    <h2>Home</h2>
    <h2>Hi, {{username}}</h2>
    <h2></h2>
  </div>
</template>
<script>
import axios from "axios";

export default {
  name: "home",
  data() {
    return {
      username: "",
      email: "",
    };
  },
  mounted() {
    const response = axios.get("user").then((res) => {
      const result = res.data.user;
      console.log({res});
      this.username = result.username;
      console.log({username: this.username});
      console.log(this);
      //  this.fetchData();
    }).catch(err => {
        console.error({err})
    });
  },
  //    watch: {
  //     // call again the method if the route changes
  //     '$route': 'fetchData'
  //   },
  //   methods:{
  //       fetchData(){
  //           this.username = this.$route.username;
  //       }
  //   }
};
</script>