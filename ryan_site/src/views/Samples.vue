<template>
  <div class="about">
    <div id="card_container">
    <b-container class="bv-example-row">
      <b-row>
        <b-col v-for="sample in samples" :key="sample.id" style="padding:0%;" >
          <b-card
            tag="article"
            style="max-width: 20rem; min-height:20rem; max-height: 20rem; padding:0%; margin:0%;"
            class="mb-2"
            :id="sample.id"
            @click="toggleModal"
          >
            <img style="max-width:17rem; margin:0%; margin-bottom:10%;" v-bind:src="require('../assets/' + sample.image)" />
            <b-card-title>{{sample.title}}</b-card-title>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
    </div>
    <div id="modal-1" ref="my-modal" v-if="!isHidden" style="color:white; border-radius:3px;">
      <div id="x-button" style="width:5rem; height:5rem; margin-top:2%; margin-right:1%; float:right; cursor:pointer;" @click="hideModal">
        <h3>X</h3>
      </div>
      <h4 style="margin-left:5%; margin-top:2%; width:50%; height:5%; text-align:left; font-weight:400;">{{modal_title}}</h4>
      <video-embed :src="video_src" style="max-width:25rem; border:2px #DDDDDD solid; border-radius:2px; opacity:.9; margin-left:5%; margin-top:1%;"></video-embed>
    </div>
  </div>
</template>

<style scoped>
  #card_container{
    margin-top:5%;
  }

  /deep/ #modal-1{
    opacity:1;
    width:95%;
    height:95%;
    margin:auto;
    background-color:rgb(50, 200, 175);
    bottom: 0;
    left: 0;
    position: fixed;
    right: 0;
    top: 0;
    z-index: 999;
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
  methods: {
    showModal () {
      this.$refs['my-modal'].show()
    },
    hideModal () {
      this.isHidden = true
      console.log('HIDE')
    },
    toggleModal () {
      // We pass the ID of the button that we want to return focus to
      // when the modal has hidden
      this.video_src = this.$data.samples[event.currentTarget.id].video
      this.modal_title = this.$data.samples[event.currentTarget.id].title
      this.isHidden = !this.isHidden
      // this.$refs['my-modal'].toggle('#toggle-btn')
    }
  },
  data () {
    return {
      samples: sampleData,
      video_src: 'https://www.youtube.com/watch?v=toZrOkcICpk',
      modal_title: '',
      modal_data: '',
      isHidden: true
    }
  }
}

</script>
