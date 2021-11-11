<template>
  <section>
    <base-card>
      <template v-slot:header>
        <h3>Course goals:</h3>
      </template>
      <ul>
        <li v-for="goal in goals" :key="goal.id">
          <slot :item="goal" itemDesc="Lorem.impsum"></slot>
        </li>
      </ul>
    </base-card>
  </section>
</template>

<script>
export default {
  data() {
    return {
      goals: ["Finish the course", "Learn Vue.js"],
    };
  },
  mounted() {
    console.log(this.$slots);
  },
};
</script>
