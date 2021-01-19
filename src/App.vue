<template>
  <div class="appt">
    {{ message }}
    <compx > </compx>
    <compy> </compy>
  </div>
</template>

<script>
import comp2 from './comp2.vue'
import comp3 from './comp3.vue'

export default {
  data: function() {
    return {
      message: 'Hello World5'
    };
  },
  components: {
    'compx': comp2,
    'compy': comp3
  }
};
</script>

<style>
.appt {
  font-size: 12px;
  font-family: 'Roboto', sans-serif;
  color: blue;
}
</style>
