<template>
  <section v-if="user">
    <div class="card">
      <h2>Name: {{user.name}}</h2>
      <h3>Email: {{user.email}}</h3>
      <h3>Phone: {{user.phone}}</h3>
      <h3>City:{{user.address.city}}</h3>
      <h3>Company: {{user.company.name}}</h3>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Detail',
  data() {
    return {
      user: null
    }
  },
  created() {
    this.getUser();
  },
  methods: {
    async getUser() {
      const path = location.pathname.split('/');
      const id = path[path.length - 1];

      const response = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
      this.user = await response.json();
    }
  }
}
</script>

<style scoped>
  section {
    width: 800px;
    margin: 0 auto;
  }
  .card {
    display: block;
    background: #f8f8f8;
    margin-top: 20px;
    margin-bottom: 20px;
    padding: 60px;
    border-radius: 6px;
    box-shadow: 3px 3px 3px #d0d0d0;
    border-bottom: 3px solid #e0e0e0;
  }

  h2 {
    margin-bottom: 20px;
  }

  h3 {
    margin-bottom: 10px;
  }
</style>
