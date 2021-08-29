<template>
    <div>
        <br />
        <div v-for="work in workplaces" :key="work.id">
            <h4>{{work.role}}</h4>
            <h5>{{work.company}}</h5>
            <h5>{{work.time}}</h5>
            <ul>
                <li v-for="point in work.points" :key="point">{{point}}</li>
            </ul>
            <br />
            <br />
        </div>
    </div>
</template>

<script>
import workData from '@/data/work_data.json'

export default {
  data () {
    return {
      workplaces: workData
    }
  }
}
</script>

<style scoped>
    ul {
        text-align: left;
        list-style-type:none;
        padding-left:5%;
    }
    h4 {
        text-align: left;
        padding-left: 5%;
        color:rgb(69, 212, 198) !important;
        font-weight: 100;
    }
    h5 {
        text-align: left;
        padding-left:5%;
    }
</style>
