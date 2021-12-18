<template>
  <h1>Jobs</h1>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id" class="job">
      <router-link
        :to="{
          name: 'JobDetails',
          params: { id: job.id },
        }"
      >
        <h2>{{ job.title }}</h2>
      </router-link>
    </div>
  </div>
  <div v-else>
    <p>Loading jobs...</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    fetch('http://localhost:3000/jobs')
      .then((response) => response.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style scoped>
.job {
  cursor: pointer;
  margin: 10px auto;
  max-width: 400px;
  padding: 10px;
  background: #2c3e50;
  border-radius: 10px;
}
a {
  text-decoration: none;
  color: #f1f1f1;
  transition: 0.3s;
}
a:hover {
  color: #ff4b5c;
}
</style>
