<style>
</style>
<template>
  <v-container>
    <v-container style="height: 2vh"> </v-container>

    <v-layout align-center justify-center wrap>
      <v-flex xs12 lg5 rounded-lg pa-5>
        <v-container pa-5>
          <form>
            <h1>Escríbenos</h1>
            <v-text-field
              v-model="name"
              :error-messages="nameErrors"
              :counter="20"
              label="Nombre"
              required
              @input="$v.name.$touch()"
              @blur="$v.name.$touch()"
            ></v-text-field>
            <v-text-field
              v-model="email"
              :error-messages="emailErrors"
              label="E-mail"
              required
              @input="$v.email.$touch()"
              @blur="$v.email.$touch()"
            ></v-text-field>
            <v-select
              v-model="select"
              :items="items"
              :error-messages="selectErrors"
              label="¿Que te interesa más?"
              required
              @change="$v.select.$touch()"
              @blur="$v.select.$touch()"
            ></v-select>
            <v-checkbox
              v-model="checkbox"
              :error-messages="checkboxErrors"
              label="Aceptar términos y condiciones"
              required
              @change="$v.checkbox.$touch()"
              @blur="$v.checkbox.$touch()"
            ></v-checkbox>

            <v-btn class="mr-4" @click="submit"> Enviar </v-btn>
            <!-- <v-btn @click="clear"> borrar </v-btn> -->
          </form>
        </v-container>
      </v-flex>
      <v-flex xs12 lg6 pa-5>
        <v-layout wrap>
          <v-flex v-for="staff in staffs" :key="staff.id" xs6 sm4 md3 lg3>
            <v-img class="fill-height" :src="staff.foto"></v-img>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
    <v-container style="height: 8vh"> </v-container>
  </v-container>
</template>
<script>
import { validationMixin } from "vuelidate";
import { required, maxLength, email } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],

  validations: {
    name: { required, maxLength: maxLength(10) },
    email: { required, email },
    select: { required },
    checkbox: {
      checked(val) {
        return val;
      },
    },
  },

  data: () => ({
    staffs: [
      {
        id: 1,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-31-1-300x300.jpg",
      },
      {
        id: 2,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-2-300x300.jpg",
      },
      {
        id: 3,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/09/Danteazul-300x300.jpg",
      },
      {
        id: 4,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-32-1.jpg",
      },
      {
        id: 5,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-30-1-300x300.jpg",
      },
      {
        id: 6,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-29-1-300x300.jpg",
      },
      {
        id: 7,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-25-1-300x300.jpg",
      },
      {
        id: 8,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-24-1-300x300.jpg",
      },
      {
        id: 9,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-23-1-300x300.jpg",
      },
      {
        id: 10,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-27-1-300x300.jpg",
      },
      {
        id: 11,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-1-300x300.jpg",
      },
      {
        id: 12,
        foto: "https://yapaydigital.pe/wp-content/uploads/2021/11/PerfilYapay-12-de-12-235x300.jpg",
      },
    ],
    name: "",
    email: "",
    select: null,
    items: [
      "Marketing digital",
      "Diseño gráfico",
      "Audiovisual",
      "Web y Seo",
      "Coaching y aprendizaje",
      "Fotografía",
      "Marketing y publicidad",
    ],
    checkbox: false,
  }),

  computed: {
    checkboxErrors() {
      const errors = [];
      if (!this.$v.checkbox.$dirty) return errors;
      !this.$v.checkbox.checked && errors.push("You must agree to continue!");
      return errors;
    },
    selectErrors() {
      const errors = [];
      if (!this.$v.select.$dirty) return errors;
      !this.$v.select.required && errors.push("Requerido");
      return errors;
    },
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.maxLength &&
        errors.push("Name must be at most 10 characters long");
      !this.$v.name.required && errors.push("Name is required.");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail");
      !this.$v.email.required && errors.push("E-mail is required");
      return errors;
    },
  },

  methods: {
    submit() {
      this.$v.$touch();
    },
    // clear() {
    //   this.$v.$reset();
    //   this.name = "";
    //   this.email = "";
    //   this.select = null;
    //   this.checkbox = false;
    // },
  },
};
</script>