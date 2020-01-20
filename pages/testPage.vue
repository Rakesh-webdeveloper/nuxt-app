<template>
    <div>
  Name: {{ fullName }}
  Message: {{ message }}
</div>
</template>

<script lang="ts">
interface User {
  firstName: string;
  lastName: number;
}
import Vue from 'vue'
export default Vue.extend({
  name: 'TestComp',
  props: {
    user: {
      type: Object,
      required: true
    } as PropOptions<User>
  },

  data () {
    return {
      message: 'This is a message'
    }
  },

  computed: {
    fullName (): string {
      return `${this.user.firstName} ${this.user.lastName}`
    }
  }
});
</script>
