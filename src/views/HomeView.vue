<template>
  <h1>Home Page</h1>

 

  <div class="card bg-light" style="width: 18rem; position:relative; left: 40%;">
    <img class="card-img-top" src="..." alt="Card image cap" />
    <div class="card-body">
      <h5 class="card-title">User Information</h5>
      <p class="card-text">
        Lastname: {{ user.lname }}
        <br />
        Firstname: {{ user.fname }}
        <br />
        Mobile: {{ user.mobile }}
        <br />

        Course: {{ user.course }}
        <br />
        Year: {{ user.year }}
        <br />
      </p>
      <p></p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>

<script>
import { useAuthStore } from "../stores/auth";
import { useRouter } from "vue-router";

export default {
  setup() {
    const { user, token } = useAuthStore();
    const router = useRouter();

    if (token == "") {
      router.replace("/login");
    }

    return {
      user,
      token,
    };
  },
};
</script>

<style></style>
