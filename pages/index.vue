<template>
  <v-card>
    <v-tabs v-model="tab" background-color="blue darken-4" grow color="white ">
      <v-tab v-for="item in items" :key="item.tab" class="tabHeaderFont">
        {{ item.tab }}
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
        <component :is="item.component" />
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script>
import Calendar from "~/components/Calendar.vue";
import List from "~/components/List.vue";
export default {
  name: "IndexPage",
  data() {
    return {
      tab: null,
      items: [
        // { tab: "Games", component: "Games Content" },
        { tab: "Standings", component: List },
        { tab: "Schedule", component: Calendar },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nova+Oval&display=swap");
.tabHeaderFont {
  font-family: "Nova Oval";
}
</style>
