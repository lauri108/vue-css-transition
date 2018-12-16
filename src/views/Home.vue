<template>
  <div class="home">
    <data-view></data-view>
  </div>
</template>

<script>
// @ is an alias to /src
import DataView from '@/components/DataView.vue';

export default {
  name: 'home',
  components: {
    DataView,
  },
};
</script>
