<template>
  <h1>Page secrète</h1>
</template>


<script>
export default function({ store, redirect }) {
    if (!store.state.auth.loggedIn) {
      return redirect("/auth/login");
    }
}
</script>

