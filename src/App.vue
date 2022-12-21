<script setup lang="ts">
import useVuelidate from "@vuelidate/core";
import { required } from "@vuelidate/validators";
import { ref } from "vue";

const rules = {
  name: {
    required
  },
  address: {
    city: { required },
    street: { required },
  },
  secondAddress: {
    city: { required },
    street: { required }
  }
};

interface UserForm {
  name: string;
  address: {
    city: string;
    street: string;
  }
  secondAddress?: {
    city: string;
    street: string;
  }
}

const userForm = ref<UserForm>({
  name: '',
  address: {
    city: '',
    street: ''
  },
  secondAddress: {
    city: '',
    street: ''
  }
})

const v$ = useVuelidate(rules, userForm);
</script>

<template>
  <form>
    
  </form>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
