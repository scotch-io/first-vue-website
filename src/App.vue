<template>
  <div id="app">
    <SiteNav/>
    <router-view/>
  </div>
</template>

<script>
import SiteNav from "./components/SiteNav";

export default {
  components: {
    SiteNav
  }
};
</script>
