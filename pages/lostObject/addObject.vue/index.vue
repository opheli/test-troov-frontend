<template>

  <div>
  
    <b-container>

      <h3>Objet à enregistrer</h3>

      <b-form-group class="m-2" id="input-group-2" label-for="input-2">

        <b-form-input
          class="m-5"
          id="input-2"
          v-model="registerData.name"
          placeholder="Entrer le nom de l'objet"
          required
        >
        </b-form-input>

        <b-form-textarea
          class="m-5"
          id="textarea"
          v-model="registerData.description"
          placeholder="Entrer la description de l'objet"
          rows="3"
          max-rows="6"
        >
        </b-form-textarea>

        <button
          v-on:click="submit()"
          type="submit"
          class="btn btn-primary w-100 m-5">
          Enregistrer l'objet
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
        name: "",
        description: "",
      },
    };
  },
  methods: {
    async submit() {
      try {
        const object = await this.$axios.$post(
          "http://localhost:8000/posts/:id_post/objects", {
          name: this.registerData.name,
          description: this.registerData.description,
        });
        console.log(object);
      } catch (err) {
        console.log(err);
      }
    },
  },
};

</script>