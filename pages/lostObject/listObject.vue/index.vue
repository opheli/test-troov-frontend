<template>

  <div>
     
      <b-container>

        <h3>Liste des objets trouvés</h3>

        <b-list-group class="m-5" type="light">

          <b-list-group-item
            class="d-flex justify-content-between align-items-center"
            v-for="object of objects"
            :key="object"
          >
            <h6> {{ object.name }} </h6>
            <br>
            <p> {{ object.description }} </p> 
           
          </b-list-group-item>

        </b-list-group>

      </b-container>

  </div>

</template>

<script>

export default {
  data() {
    return {
      objects: [],
    };
  },
  async fetch() {
    this.objects = await fetch(
      "http://localhost:8000/posts/:id_post/objects"
    ).then((res) => res.json());
  },
};

</script>