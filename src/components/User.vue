<template>
  <div class="card">
    <div class="card-image has-text-centered">
      <img :src="user.avatar_url">
    </div>
    <div class="card-content">
      <h2>
        <a :href="user.html_url">{{ user.login }}</a>
      </h2>
    </div>
  </div>
</template>

<script>
export default {
  props: ["user"]
};
</script>

<style lang="scss" scoped>
img {
  max-height: 150px;
  margin: 0 auto;
}
</style>
