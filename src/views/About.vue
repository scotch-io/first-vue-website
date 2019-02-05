<template>
  <div class="about section">
    <div class="container">
      <h1>This is an about page</h1>
      <div class="columns">
        <div class="column" v-for="user in users" :key="user.login">
          <User/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import User from "@/components/User";

export default {
  // register components
  components: { User },

  // data for this component goes in here
  data() {
    return {
      users: null
    };
  },

  // lifecycle hook for when this component is added to the view
  mounted() {
    // go grab data from github
    fetch("https://api.github.com/users?per_page=12")
      .then(resp => resp.json()) // unwrap the fetch response
      .then(data => {
        // what does this data look like?
        console.log(data);
        this.users = data; // bind users to our component
      });
  }
};
</script>
