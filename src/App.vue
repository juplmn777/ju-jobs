<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/jobs">Jobs</router-link>
  </div>

  <div class="btn-container">
    <button @click="redirect" class="redirection-btn">Redirect</button>
    <button @click="backward" class="backward-btn">Go Back</button>
    <button @click="forward" class="forward-btn">Go Forward</button>
  </div>

  <router-view />
</template>
<script>
export default {
  methods: {
    redirect() {
      this.$router.push({ name: 'Home' });
    },
    backward() {
      this.$router.go(-1);
    },
    forward() {
      this.$router.go(1);
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  background: #ff4b5c;
  border: 1px solid #ff4b5c;
  color: #f1f1f1;
  padding: 10px;
  border-radius: 10px;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  background: #3e8e7e;
  color: #f1f1f1;
  border: 1px solid #3e8e7e;
}

.btn-container {
  max-width: 400px;
  margin: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}

button {
  padding: 10px;
  border-radius: 5px;
  font-weight: bold;
  transition: 0.3s;
  color: #f1f1f1;
  text-transform: uppercase;
  cursor: pointer;
}

.redirection-btn {
  border: 1px solid #333;
  background: #333;
}

.backward-btn {
  border: 1px solid #e78a1f;
  background: #e78a1f;
}

.forward-btn {
  border: 1px solid #740e74;
  background: #740e74;
}

button:hover {
  background: #f1f1f1;
}

.redirection-btn:hover {
  border: 1px solid #333;
  color: #333;
}

.backward-btn:hover {
  border: 1px solid #e78a1f;
  color: #e78a1f;
}

.forward-btn:hover{
  border: 1px solid #740e74;
  color: #740e74;
}
</style>
