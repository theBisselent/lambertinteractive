<template>
  <div class="about">
    <div id="tab_div">
      <b-card no-body id='work_tabs'>
        <b-tabs card fill  class='exp_tab_content'>
          <b-tab title="Work" active class='exp_tab_content'>
            <b-card-text  class='exp_tab_content'>
              <Resume />
            </b-card-text>
          </b-tab>
          <b-tab title="Education"  class='exp_tab_content'>
            <b-card-text  class='exp_tab_content'>
              <Schools />
            </b-card-text>
          </b-tab>
        </b-tabs>
      </b-card>
    </div>
  </div>
</template>

<script>
import Resume from '@/components/Resume.vue'
import Schools from '@/components/School.vue'

export default {
  components: {
    Resume,
    Schools
  }
}
</script>

<style scoped>
  #work_tabs {
    background:transparent !important;
    height:100%;
  }

  .exp_tab_content {
    height:100%;
    margin-top: 1%;
  }

  #tab_div {
    background:transparent;
    height:100%;
  }

  .nav a.router-link-exact-active {
        color: #42b983;
    }
</style>
