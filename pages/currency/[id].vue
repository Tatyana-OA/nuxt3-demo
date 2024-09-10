<script setup>
const route = useRoute();
const { data } = await useFetch("/api/ticker?id=" + route.params.id);
const coin = data.value[0];
</script>
<template>
  <div>
    <h2>{{ coin.name }} Detail page</h2>
    <table>
      <thead>
        <tr>
          <th>Symbol</th>
          <th>Rank</th>
          <th>Price - US $</th>
          <th>Market Cap - US $</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{{ coin.symbol }}</td>
          <td>{{ coin.rank }}</td>
          <td>{{ coin.price_usd }}</td>
          <td>{{ coin.market_cap_usd }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
div {
  padding: 20px;
  font-family: Arial, sans-serif;
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 1.75rem;
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
</style>
