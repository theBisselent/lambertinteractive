<template>
    <div>
        <br />
        <div  id="container" v-for="school in schools" :key="school.id">
            <h4>{{school.course}}</h4>
            <h5>{{school.school}}</h5>
            <h5>{{school.time}}</h5>
            <ul>
                <li v-for="point in school.points" :key="point">{{point}}</li>
            </ul>
            <br />
            <br />
        </div>
    </div>
</template>

<script>
import schoolData from '@/data/school_data.json'

export default {
  data () {
    return {
      schools: schoolData
    }
  }
}
</script>

<style scoped>
    #container{
        height:100%;
    }
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
