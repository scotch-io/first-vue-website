<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div v-for="user in users" :key="user.login">
      <h2>{{ user.login }}</h2>
    </div>
  </div>
</template>

<script>
export default {
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
