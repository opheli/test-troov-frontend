<template>

  <div>

    <b-container>

      <h3>Inscription</h3>

      <b-form-group class="m-2" id="input-group-2" label-for="input-2">
        
        <b-form-input
          class="m-5"
          id="email"
          type="email"
          v-model="registerData.email"
          placeholder="Entrer votre email"
          required
        >
        </b-form-input>

        <b-form-input
          class="m-5"
          id="password"
          type="password"
          v-model="registerData.password"
          placeholder="Entrer votre mot de passe"
          required
        >
        </b-form-input>
       
        <button
          v-on:click="register()"
          type="submit"
          class="btn btn-primary w-100 m-5"
          >
          S'enregistrer
        </button>

      </b-form-group>

    </b-container>

  </div>

</template>

<script>

export default {
  data() {
    return {
      registerData: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    async register() {
      try {
        const user = await this.$axios.$post(
          "http://localhost:8000/user/register",
          {
            email: this.registerData.email,
            password: this.registerData.password,
          }
        );
      } catch (err) {
        console.log(err);
      }
    },
  },
};

</script>
