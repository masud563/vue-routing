<template>
  <h1>Jobs</h1>
  <div v-if="jobs">
    <div v-for="job in jobs" :key="job.id" class="job">
    <router-link :to="{ name: 'jobDetails', params:{id:job.id}}">
      <h2>{{job.title}}</h2>
    </router-link>
  </div>
  <div v-else>
    <p>Loading</p>
  </div>
  </div>
  
</template>

<script>
export default {
  data() {
    return{
      jobs:[]
    }
  },

  mounted() {
    fetch('http://localhost:3000/jobs')
      .then(res=>res.json())
      .then(data=>this.jobs=data)
      .catch(err=>console.log(err.message))
  }
}
</script>

<style>
  .job h2 {
    padding: 20px;
    background-color: #f4f4f4;
    width: 600px;
    margin: 5px auto;
    border-radius: 10px;
  }

  .job h2:hover {
    background-color: #ddd;
  }

  .job a{
    text-decoration: none;
    color: black;
  }
</style>