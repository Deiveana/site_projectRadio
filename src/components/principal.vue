<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="name"
      :rules="nameRules"
      label="Name"
      required
    ></v-text-field>
    
    <v-text-field
      v-model="Empresa"
      :rules="empresaRules"
      label="Empresa"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

    <v-text-field
      v-model="celular"
      :rules="celularRules"
      label="Celular"
      type="phone"
    ></v-text-field>
    <v-checkbox
      v-model="checkbox"
      label="Este numero é seu Whatsapp?"
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
  </v-form>
</template>

<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Este campo precisa ser preenchido',
        v => (v && v.length <= 10) || 'Precisa ter mais de 10 caracteres',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail precisa ser preenchido',
        v => /.+@.+\..+/.test(v) || 'E-mail precisa ser valido',
      ],
      celular: null,
      checkbox: true,
      Empresa: '',
      empresaRules: [
        v => !!v || 'Este campo precisa ser preenchido',
        v => (v && v.length <= 3) || 'Precisa ter mais de 3 caracteres',
      ],
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

<style>
.v-form{
  border: 1px aquamarine;
}
</style>