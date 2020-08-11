<template>
  <div>
    <h1>PDP</h1>
    <p>ID: {{ id }}</p>
    <p>Slug: {{ slug }}</p>
    <div v-for="role in roles" :key="role.id">
      <p>{{ role.name }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios'

export default Vue.extend({
  layout: 'cf',
  data() {
    return {
      id: '',
      slug: '',
      roles: []
    }
  },
  async asyncData(context: any) {
    const responseRoles = await axios.get(
        `https://private-d876a6-samplecrud.apiary-mock.com/v1/master/roles`
      )

    return {
      id: context.params.id,
      slug: context.params.slug,
      roles: responseRoles.data.data,
    }
  }
})
</script>