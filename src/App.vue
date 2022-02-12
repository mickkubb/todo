<template>
  <v-app>
    <v-app-bar app color="#6A76AB" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://upload.wikimedia.org/wikipedia/th/thumb/d/db/Chiang_Mai_University.svg/800px-Chiang_Mai_University.svg.png"
          transition="scale-transition"
          width="60"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn to="/" text>
        <span class="mr-2">หน้าแรก</span>
      </v-btn>
      <v-btn to="/todo" text>
        <span class="mr-2">ลงทะเบียน</span>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
