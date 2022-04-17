<template>
  <h2>manage Goal</h2>
  <input type="text" ref="goal" />
  <button @click="setGoal">Set Goal</button>
  <teleport to="body">
    <ErrorAlert v-if="inputisValid">
      <h1>input can not be empty</h1>
      <p>write something so the error goes away</p>
      <button @click="confirmError">okay</button>
    </ErrorAlert>
  </teleport>
</template>

<script>
import ErrorAlert from './ErrorAlert.vue';

export default {
  components: {
    ErrorAlert,
  },

  data() {
    return {
      inputisValid: false,
    };
  },
  methods: {
    setGoal() {
      const enterdValue = this.$refs.goal.value;
      if (!enterdValue) {
        this.inputisValid = true;
      }
    },
    confirmError() {
      this.inputisValid = false;
    },
  },
};
</script>
