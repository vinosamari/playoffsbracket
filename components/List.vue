<template>
  <v-list two-line>
    <v-list-item-group
      v-model="selected"
      active-class="blue--text text--accent-4"
      multiple
      
    >
      <v-subheader>Conference Standings</v-subheader>

      <template v-for="(item, index) in items">
        <v-list-item :key="item.TeamID" class="text-left">
          <template v-slot:default="{ active }">
            <v-list-item-content>
              <img :src="item.WikipediaLogoUrl" :alt="item.Key">
              <v-list-item-title> {{ item.Key }}</v-list-item-title>

              <v-list-item-subtitle class="text--primary">{{
                item.City
              }}</v-list-item-subtitle>

              <v-list-item-subtitle>{{ item.Name }}</v-list-item-subtitle>
            </v-list-item-content>


              <v-icon v-if="!active" color="grey lighten-1">
                mdi-star-outline
              </v-icon>

              <v-icon v-else color="blue darken-3"> mdi-star </v-icon>
            </v-list-item-action>
          </template>
        </v-list-item>

        <v-divider v-if="index < items.length - 1" :key="index"></v-divider>
      </template>
    </v-list-item-group>
  </v-list>
</template>

<script>
export default {
  data: () => ({
    selected: [2],
    items: [
      {
        TeamID: 1,
        Key: "WAS",
        Active: true,
        City: "Washington",
        Name: "Wizards",
        LeagueID: 3,
        StadiumID: 1,
        Conference: "Eastern",
        Division: "Southeast",
        PrimaryColor: "002B5C",
        SecondaryColor: "E31837",
        TertiaryColor: "C4CED4",
        QuaternaryColor: "FFFFFF",
        WikipediaLogoUrl:
          "https://upload.wikimedia.org/wikipedia/en/0/02/Washington_Wizards_logo.svg",
        WikipediaWordMarkUrl: null,
        GlobalTeamID: 20000001,
        NbaDotComTeamID: 1610612764,
      },
    ],
  }),
};
</script>

<style scoped>
img{
  height: 50px;
  width: 50px;
  border-radius: 50%;
}
</style>
