<script setup>
const { data } = await useFetch("/api/tickers?limit=10");
</script>

<template>
  <main>
    <h1>Crypto Data</h1>

    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Symbol</th>
          <th>Price</th>
          <th>Details</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="currency in data.data" :key="currency.id">
          <td>{{ currency.name }}</td>
          <td>{{ currency.symbol }}</td>
          <td>{{ currency.price_usd }}</td>
          <td>
            <NuxtLink :to="'/currency/' + currency.id">{{
              currency.id
            }}</NuxtLink>
          </td>
        </tr>
      </tbody>
    </table>
  </main>
</template>

<style scoped>
main {
  padding: 20px;
  font-family: Arial, sans-serif;
}

h1 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 2rem;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin: 0 auto;
  text-align: left;
  font-size: 1rem;
}

th,
td {
  padding: 12px 15px;
  border: 1px solid #ddd;
}

thead {
  background-color: #f5f5f5;
}

tr:nth-child(even) {
  background-color: #f9f9f9;
}

tr:hover {
  background-color: #f1f1f1;
}

a {
  color: #3498db;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
</style>
