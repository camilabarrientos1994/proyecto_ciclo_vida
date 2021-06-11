<template>
  <div>
    <v-container>
      <v-app id="inspire">
        <v-form6
            ref="form"
            v-model="valid"
            lazy-validation
        > <h1 >Formulario de Registro Médico</h1>
          <v-text-field
              v-model="name"
              :counter="10"
              :rules="nameRules"
              label="Name"
              required
          ></v-text-field>

          <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              required
          ></v-text-field>
          <v-text-field
              v-model="estado_civil"
              :rules="estado_civilRules"
              label="estado_civil"
              required
          ></v-text-field>
          <v-text-field
              v-model="sexo"
              :rules="sexoRules"
              label="sexo"
              required
          ></v-text-field>
          <v-text-field
              v-model="Fecha_nacimiento"
              :rules="Fecha_nacimientoRules"
              label="Fecha_nacimiento"
              required
          ></v-text-field>
          <v-text-field
              v-model="Lugar_nacimiento"
              :rules="Lugar_nacimientoRules"
              label="Lugar_nacimiento"
              required
          ></v-text-field>
          <v-text-field
              v-model="Edad"
              :rules="EdadRules"
              label="Edad"
              required
          ></v-text-field>
          <v-text-field
              v-model="Rut"
              :rules="RutRules"
              label="Rut"
              required
          ></v-text-field>
          <v-text-field
              v-model="Direccion"
              :rules="DireccionRules"
              label="Direccion"
              required
          ></v-text-field>
          <v-text-field
              v-model="Celular"
              :rules="CelularRules"
              label="Celular"
              required
          ></v-text-field>
          <v-text-field
              v-model="Telefono_emergencia"
              :rules="Telefono_emergenciaRules"
              label="Telefono_emergencia"
              required
          ></v-text-field>
          <v-text-field
              v-model="Correo"
              :rules="CorreoRules"
              label="Correo"
              required
          ></v-text-field>
          <v-text-field
              v-model="Enfermedades_cronicas"
              :rules="Enfermedades_cronicasRules"
              label="Enfermedades_cronicas"
              required
          ></v-text-field>
          <v-text-field
              v-model="Medicamentos_permantentes"
              :rules="Medicamentos_permantentesRules"
              label="Medicamentos_permantentes"
              required
          ></v-text-field>
          <v-text-field
              v-model="Alergias"
              :rules="AlergiasRules"
              label="Alergias"
              required
          ></v-text-field>
          <v-text-field
              v-model="Intervencion_quirurgica"
              :rules="Intervencion_quirurgicaRules"
              label="Intervencion_quirurgica"
              required
          ></v-text-field>
          <v-text-field
              v-model="Grupo_sanguineo"
              :rules="Grupo_sanguineoRules"
              label="Grupo_sanguineo"
              required
          ></v-text-field>
          <v-text-field
              v-model="Ultimo_control"
              :rules="Ultimo_controlRules"
              label="Ultimo_control"
              required
          ></v-text-field>
          <v-text-field
              v-model="Prevision"
              :rules="PrevisionRules"
              label="Prevision"
              required
          ></v-text-field>
          <v-text-field
              v-model="Seguro_salud"
              :rules="Seguro_saludRules"
              label="Seguro_salud"
              required
          ></v-text-field>
          <v-text-field
              v-model="Vacunas"
              :rules="VacunasRules"
              label="Vacunas"
              required
          ></v-text-field>

          <v-select
              v-model="select"
              :items="items"
              :rules="[v => !!v || 'Item is required']"
              label="Item"
              required
          ></v-select>


          <v-checkbox
              v-model="checkbox"
              :rules="[v => !!v || 'You must agree to continue!']"
              label="Do you agree?"
              required
          ></v-checkbox>

          <v-btn
              :disabled="!valid"
              color="success"
              class="mr-4"
              @click="validate"
          >
            Validate
          </v-btn>

          <v-btn
              color="error"
              class="mr-4"
              @click="reset"
          >
            Reset Form
          </v-btn>

          <v-btn
              color="warning"
              @click="resetValidation"
          >
            Reset Validation
          </v-btn>
        </v-form6>
      </v-app>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Formulario",
  data: () => ({
    valid: true,
    name: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    estado_civil: '',
    estado_civilRules: [
      v => !!v || 'estado civil is required',
      v => (v && v.length <= 20) || 'Name must be less than 10 characters',
    ],
    sexo:'',
    sexoRules: [
      v => !!v || 'Sexo is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Fecha_nacimiento: '',
    Fecha_nacimientoRules: [
      v => !!v || 'Fecha de nacimiento is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Lugar_nacimiento: '',
    Lugar_nacimientoRules: [
      v => !!v || 'Lugar nacimiento is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Edad: '',
    EdadRules: [
      v => !!v || 'Edad is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Rut: '',
    RutRules: [
      v => !!v || 'Rut is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Direccion: '',
    DireccionRules: [
      v => !!v || 'Direccion is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Celular: '',
    CelularRules: [
      v => !!v || 'Celular is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Telefono_emergencia: '',
    Telefono_emergenciaRules: [
      v => !!v || 'Telefono emergencia is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Correo: '',
    CorreoRules: [
      v => !!v || 'Correo is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Enfermedades_cronicas: '',
    Enfermedades_cronicasRules: [
      v => !!v || 'Telefono emergencia is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Medicamentos_permantentes: '',
    Medicamentos_permantentesRules: [
      v => !!v || 'Telefono emergencia is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Alergias: '',
    AlergiasRules: [
      v => !!v || 'Telefono emergencia is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Intervencion_quirurgica: '',
    Intervencion_quirurgicaRules: [
      v => !!v || 'Intervencion_quirurgica is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Grupo_sanguineo: '',
    Grupo_sanguineoRules: [
      v => !!v || 'Grupo_sanguineo is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Ultimo_control: '',
    Ultimo_controlRules: [
      v => !!v || 'Ultimo_control is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Prevision: '',
    PrevisionRules: [
      v => !!v || 'Prevision is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Seguro_salud: '',
    Seguro_saludRules: [
      v => !!v || 'Seguro_salud is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    Vacunas: '',
    VacunasRules: [
      v => !!v || 'Vacunas is required',
      v => (v && v.length <= 50) || 'Name must be less than 10 characters',
    ],
    select: null,
    items: [
      'Item 1',
      'Item 2',
      'Item 3',
      'Item 4',
    ],
    checkbox: false,
  }),

  methods: {
    validate () {
      this.$refs.form.validate()
    },
    reset () {
      this.$refs.form.reset()
    },
    resetValidation () {
      this.$refs.form.resetValidation()
    },
  },
}
</script>

<style scoped>

</style>