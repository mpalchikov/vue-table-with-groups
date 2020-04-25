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
import _ from "lodash";
export default {
  props: ["items", "groups"],
  computed: {
    colsCount() {
      return Object.keys(this.items).length;
    },
    groupedItems() {
      return _.groupBy(this.items, i => {
        return this.groups.map(g => i[g]);
      });
    },
    flatItems() {
      let result = [];
      for (let key in this.groupedItems) {
        key.split(",").forEach((k, index) => {
          result.push({ group: k, level: index });
        });
        result = result.concat(this.groupedItems[key]);
      }
      return result;
    }
  }
};
</script>
