<script>
export default {
  name: "App",

  data: () => ({
    page: "home",
    pages: [
      { title: "Home", value: "home" },
      { title: "About", value: "about" }
    ]
  }),
  methods: {
    logChanges() {
      console.log("ch-ch-ch-ch-changes");
    }
  }
};
</script>

<template>
  <v-app>
    <v-navigation-drawer permanent>
      <v-tabs v-model="page" direction="vertical">
        <v-tab
          v-for="entry in pages"
          :key="entry.value"
          :value="entry.value"
          @change="logChanges"
          >{{ entry.title }}</v-tab
        >
      </v-tabs>
    </v-navigation-drawer>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>
