<template>
  <div v-if="jobDetail">
    <h1>{{ job.title }}</h1>
    <p>The job id is {{ id}} </p>
    <p> {{ job.detail }}</p>
  </div>
  <div v-else>
    <p>Loading job details</p>
  </div>
</template>

<script>
export default {

  props: ['id'],

  data() {
    return {
      jobDetail: null
    }
  },
  
  mounted() {
    fetch('http://localhost:3000/jobs' + this.id)
      .then(res=>res.json())
      .then(data=>this.jobDetail = data)
      .catch(err=>console.log(err.message))
  }
}
</script>

<style>

</style>