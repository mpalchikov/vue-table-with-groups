<template>
  <div>
    <h1>Table With Groups</h1>
    <table border="1">
      <thead>
        <tr>
          <th>Groups: {{ groups.join("/") }}</th>
          <th>City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in items" :key="index">
          <td></td>
          <td>{{ item.city }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: ["items", "groups"]
};
</script>
