<template>
  <div class="hero is-light is-bold" :class="[size, color]">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">{{ title }}</h1>
        <h2 class="subtitle">{{ subtitle }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["size", "color", "title", "subtitle"]
};
</script>