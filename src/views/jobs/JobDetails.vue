<template>
  <div v-if="job" class="job-card">
    <h1>{{ job.title }}</h1>
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p class="load-job-card">Loading job details...</p>
  </div>
</template>

<script>
export default {
  props: ['id'],
  data() {
    return {
      job: null,
    };
  },
  mounted() {
    fetch('http://localhost:3000/jobs/' + this.id)
      .then((response) => response.json())
      .then((data) => (this.job = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style scoped>
.job-card {
  max-width: 500px;
  margin: 50px auto;
  padding: 20px;
  background: #2c3e50;
  border-radius: 10px;
  color: #f1f1f1;
}

h1 {
  font-size: 3rem;
}

p {
  font-size: 1.5rem;
  text-align: left;
}
</style>
