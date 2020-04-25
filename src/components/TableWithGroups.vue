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
        <template v-for="(item, index) in flatItems">
          <tr v-if="item.hasOwnProperty('group')" :key="index">
            <td
              :colspan="colsCount"
              :style="{ 'padding-left': `${item.level * 10}px` }"
            >
              {{ item.group }}
            </td>
          </tr>
          <tr v-else :key="index">
            <td></td>
            <td>{{ item.city }}</td>
          </tr>
        </template>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: ["items", "groups"],
  computed: {
    colsCount() {
      return Object.keys(this.items).length;
    },
    flatItems() {
      return [
        { group: "Ukraine", level: 0 },
        { group: "Donetsk Oblast", level: 1 },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Avdiivka" },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Horlivka" },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Debaltseve" },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Donetsk" },
        { group: "Lviv Oblast", level: 1 },
        { country: "Ukraine", region: "Lviv Oblast", city: "Drohobych" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Dubliany" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Zolochiv" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Kamianka-Buzka" },
        { group: "USA", level: 0 },
        { group: "Arizona", level: 1 },
        { country: "USA", region: "Arizona", city: "Phoenix" },
        { country: "USA", region: "Arizona", city: "Tucson" },
        { country: "USA", region: "Arizona", city: "Mesa" },
        { group: "Washington", level: 1 },
        { country: "USA", region: "Washington", city: "Vancouver" },
        { country: "USA", region: "Washington", city: "Kent" },
        { country: "USA", region: "Washington", city: "Everett" },
        { country: "USA", region: "Washington", city: "Rentone" }
      ];
    }
  }
};
</script>
