<template>
  <div id="app">
    <TableWithGroups :items="items" :groups="groups" />
  </div>
</template>

<script>
import TableWithGroups from "./components/TableWithGroups.vue";

export default {
  name: "App",
  components: {
    TableWithGroups
  },
  data() {
    return {
      items: [
        { country: "Ukraine", region: "Donetsk Oblast", city: "Avdiivka" },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Horlivka" },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Debaltseve" },
        { country: "Ukraine", region: "Donetsk Oblast", city: "Donetsk" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Drohobych" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Dubliany" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Zolochiv" },
        { country: "Ukraine", region: "Lviv Oblast", city: "Kamianka-Buzka" },
        { country: "USA", region: "Arizona", city: "Phoenix" },
        { country: "USA", region: "Arizona", city: "Tucson" },
        { country: "USA", region: "Arizona", city: "Mesa" },
        { country: "USA", region: "Washington", city: "Vancouver" },
        { country: "USA", region: "Washington", city: "Kent" },
        { country: "USA", region: "Washington", city: "Everett" },
        { country: "USA", region: "Washington", city: "Rentone" }
      ],
      groups: ["country", "region"]
    };
  }
};
</script>
