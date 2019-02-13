<template>
  <div class="home">
    <Hero
      size="is-fullheight"
      color="is-info"
      title="Greatest Website on Earth"
      subtitle="Better than Chocolate Cake"
    />
  </div>
</template>

<script>
import Hero from "@/components/Hero";

export default {
  name: "home",
  components: { Hero }
};
</script>
