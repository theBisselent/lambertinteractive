<template>
  <div class="about">
    <div id="card_container">
    <b-container class="bv-example-row">
      <b-row>
        <b-col v-for="sample in samples" :key="sample.id" style="padding:0%;">
          <b-card
            tag="article"
            style="max-width: 20rem; min-height:20rem; max-height: 20rem; padding:0%; margin:0%;"
            class="mb-2"
          >
            <img style="max-width:17rem; margin:0%; margin-bottom:10%;" v-bind:src="require('../assets/' + sample.image)">
            <b-card-title>{{sample.title}}</b-card-title>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
    </div>
    <b-modal id="modal-1" title="BootstrapVue">
      <h4>this is a modal</h4>
    </b-modal>
  </div>
</template>

<style scoped>
  #card_container{
    margin-top:5%;
  }

  #modal-1{
    width:90%;
    height:90%;
  }

  .mb-2:active {
    background-color:rgb(69, 212, 198);
  }

  .mb-2:hover{
    cursor: pointer;
  }
</style>

<script>
import sampleData from '@/data/sample_data.json'

export default {
  data () {
    return {
      samples: sampleData
    }
  }
}
</script>
