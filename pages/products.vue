<template>
  <div>
    <h1>Product List</h1>
    <p>{{ title }}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Products',
  layout: 'cf',
  data() {
    return {
      title: 'Ini adalah product list'
    }
  }
})
</script>