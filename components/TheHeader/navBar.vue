<template>

  <div>

    <b-navbar toggleable="lg" type="light" variant="light" class="mb-5">

       <b-navbar-brand>
       <nuxt-link
            to="/" >
      <img src="https://www.troov.com/images/logo-dark.png" alt="logo Troov" titre="logo Troov">
      </nuxt-link
            >
    </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>

        <b-navbar-nav>

          <li class="nav-item m-3">
            <nuxt-link
            to="/lostObject/listObject"
            class="nav-link"
            >Liste des objets</nuxt-link
            >
          </li>

          <li class="nav-item m-3">
            <nuxt-link
            to="/lostObject/addObject" 
            class="nav-link"
            >Ajouter un objet</nuxt-link
            >
          </li>

        </b-navbar-nav>

        <!-- Right aligned nav items -->

        <b-navbar-nav class="ml-auto">

          <b-nav-form>

            <li class="nav-item m-3">
              <nuxt-link
                class="nav-link"
                aria-current="page"
                to="/auth/login"
                >Connexion</nuxt-link
              >
            </li>

            <li class="nav-item m-3">
              <nuxt-link
                class="nav-link"
                aria-current="page"
                to="/auth/register"
                >Inscription</nuxt-link
              >
            </li>

          </b-nav-form>

        </b-navbar-nav>

      </b-collapse>

    </b-navbar>

  </div>

</template>

<script>
export default {};
</script>

