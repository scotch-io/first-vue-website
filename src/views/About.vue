<template>
  <div class="about">
    <Hero title="Welcome to Our Team" subtitle="A Small Ragtag Bunch" color="is-warning"/>

    <div class="section">
      <div class="container">
        <div class="columns is-multiline">
          <div class="column is-2" v-for="user in users" :key="user.login">
            <User v-bind:user="user"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import User from "@/components/User";
import Hero from "@/components/Hero";

export default {
  // register components
  components: { User, Hero },

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
