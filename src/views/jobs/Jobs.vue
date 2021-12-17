<template>
  <h1>Jobs</h1>
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
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        {
          title: 'Front-End Developer',
          id: 1,
          details: 'lorem',
        },
        {
          title: 'Web Designer',
          id: 2,
          details: 'lorem',
        },
        {
          title: 'Back-End Developer',
          id: 3,
          details: 'lorem',
        },
      ],
    };
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
