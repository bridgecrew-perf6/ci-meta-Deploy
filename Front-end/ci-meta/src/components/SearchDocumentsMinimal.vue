<template>
  <div class="d-flex align-items-center justify-content-center" v-if="!submit">
      <b-card
        v-if="!submit"
        title="Search"
        style="max-width: 20rem;"
        class="text-center"
        border-variant="warning"
        >
        <b-form inline >
          <label class="sr-only" for="inline-form-input-id">Id</label>
          <b-input-group class="mb-2 mr-sm-2 mb-sm-0">
          <b-form-input v-model="id" id="inline-form-input-id" placeholder="id"></b-form-input>
          </b-input-group>
          <br>
          <div class="text-center">
            <b-button v-on:click.prevent="submit= true" variant="primary">Search</b-button>
          </div>
          <br>
          <div class="text-center" style="margin-top: 20px;" v-if="loading">
          <b-spinner variant="primary"></b-spinner>
          </div>
        </b-form>
      </b-card>
  </div>
  <div v-else>
    <b-button variant="link" @click="submit = false">Back to selection</b-button>
    <br>
    <show-documents-minimal :id="id" />
  </div>
</template>

<script>
import ShowDocumentsMinimal from './ShowDocumentsMinimal.vue'
export default {
  components: { ShowDocumentsMinimal },
  name: 'SearchDocumentsMinimal',
  data () {
  return {
      id : 0,
      submit: false,
      }
  },
}
</script>

<style>

</style>