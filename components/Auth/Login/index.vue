<template>

  <div>

    <b-container>

      <h3>Connexion</h3>

      <b-form-group class="m-2" id="input-group-2" label-for="input-2">
        <b-form-input
          class="m-5"
          id="email"
          type="email"
          v-model="loginData.email"
          placeholder="Entrer votre email"
          required
        >
        </b-form-input>

        <b-form-input
          class="m-5"
          id="password"
          type="password"
          v-model="loginData.password"
          placeholder="Entrer votre mot de passe"
          required
        >
        </b-form-input>

        <button
          v-on:click="login()"
          type="submit"
          class="btn btn-primary w-100 m-5"
        >
          Se connecter
        </button>

      </b-form-group>

    </b-container>

  </div>

</template>

<script>

export default {
  data() {
    return {
      loginData: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    async login() {
      try {
        let response = await this.$axios.$post("http://localhost:8000/user/register", {
          email: this.loginData.email,
          password: this.loginData.password,
        });
        console.log(reponse);
      } catch (err) {
        console.log(err);
      }
    },
  },
};

</script>

