<template>
  <div class="importen">
    <Jonas/>
    <Jonas2/>
  </div>
</template>

<script>
// @ is an alias to /src
import Jonas from "@/components/jonas.vue";
import Jonas2 from "@/components/jonas2.vue";

export default {
  name: "importen",
  components: {
    Jonas,
    Jonas2
  }
};
</script>
