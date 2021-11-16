
<template>
  <section>
    <base-card>
      <template v-slot:header>
        <h2>Manage goals</h2>
      </template>

      <div>
        <input type="text" ref="goal" />
        <button @click="setGoal">Set goal</button>
        <teleport to="#app">
          <error-alert v-if="inputIsInvalid">
            <h2>Input is invalid</h2>
            <p>Please enter something</p>
            <button @click="confirmError">Okey</button>
          </error-alert>
        </teleport>
      </div>
    </base-card>
  </section>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";

export default {
  components: {
    ErrorAlert,
  },
  data() {
    return {
      inputIsInvalid: false,
    };
  },
  methods: {
    setGoal() {
      const enteredValue = this.$refs.goal.value;
      if (enteredValue === "") {
        this.inputIsInvalid = true;
      }
    },
    confirmError() {
      this.inputIsInvalid = false;
    },
  },
};
</script>