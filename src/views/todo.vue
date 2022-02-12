<template>
  <v-container>
    <hi mix="ลงทะเบียน" />
    <v-row>
      <v-col cols="12" sm="6" md="4">
        <v-text-field
          v-model="namestudent"
          label="ชื่อ"
          filled
          dense
        ></v-text-field>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <v-text-field
          v-model="lastname"
          label="นามสกุล"
          filled
          dense
        ></v-text-field>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <v-text-field v-model="major" label="คณะ" filled dense></v-text-field>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <v-text-field v-model="major2" label="สาขา" filled dense></v-text-field>
      </v-col>
      <v-col cols="12" sm="6" md="4">
        <v-text-field
          v-model="idstu"
          label="รหัสบัตรประชาชน"
          filled
          dense
        ></v-text-field>
      </v-col>
    </v-row>
    <v-select v-model="subject" :items="items" label="จังหวัด" solo></v-select>
    <v-container fluid>
      <v-textarea
        v-model="address"
        clearable
        clear-icon="mdi-close-circle"
        label="ที่อยู่"
        value=""
      ></v-textarea>
    </v-container>
    <v-btn class="mx-2" fab dark color="indigo" @click="addTodo()">
      <v-icon dark> mdi-plus </v-icon>
    </v-btn>

    <v-container>
      <v-list dense>
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item v-for="(item, i) in additems" :key="i">
            <v-list-item-content>
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
            <v-btn
              class="mx-2"
              fab
              dark
              small
              color="error"
              @click="deleteTodo(i)"
            >
              <v-icon dark> mdi-minus </v-icon>
            </v-btn>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-container>
  </v-container>
</template>

<script>
import hi from "../components/hi.vue";
export default {
  data() {
    return {
      subject: "",
      namestudent: "",
      lastname: "",
      address: "",
      major: "",
      major2: "",
      idstu: "",
      items: ["เชียงใหม่", "กรุงเทพ", "ตรัง", "สงขลา"],
      selectedItem: 1,
      additems: [],
    };
  },
  components: {
    hi,
  },

  methods: {
    addTodo() {
      //console.log(this.subject + this.work);
      this.additems.push({
        text:
          this.namestudent +
          " " +
          this.lastname +
          " " +
          "รหัสบัตรประชาชน" +
          this.idstu +
          "" +
          this.subject +
          " " +
          "คณะ" +
          this.major +
          " " +
          "สาขา" +
          this.major2 +
          " " +
          "ที่อยู่" +
          " " +
          this.address,
      });
    },
    deleteTodo(index) {
      this.additems.splice(index, 1);
    },
  },
};
</script>

<style></style>
