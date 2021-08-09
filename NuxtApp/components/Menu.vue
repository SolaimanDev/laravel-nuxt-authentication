<template>
  <div class="menu">
     <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
  <div class="container-fluid">
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarTogglerDemo03" aria-controls="navbarTogglerDemo03" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <nuxt-link class="navbar-brand" to="/">Navbar</nuxt-link>
    <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <nuxt-link class="nav-link active" aria-current="page" v-if="loggdIn" to="/profile">Profile</nuxt-link>
        </li>

      </ul>
    </div>
    <div class="navbar-collapse collapse w-100 order-3 dual-collapse2">
        <ul class="navbar-nav ml-auto">
            <li class="nav-item">
                <nuxt-link class="nav-link" v-if="!loggdIn" to="/login">Login</nuxt-link>
            </li>
            <li class="nav-item">
                <nuxt-link class="nav-link" v-if="!loggdIn" to="/register">Register</nuxt-link>
            </li>
            <li class="nav-item">
                <a type="button" class="nav-link" v-if="loggdIn" @click.prevent="logout">Logout</a>
            </li>
        </ul>
    </div>
  </div>
</nav>
    </div>
</template>
<script>
export default {
   computed:{
     loggdIn(){
       return this.$store.state.auth.loggedIn;
     },

   },
methods:{
 async logout()
  {
    await this.$auth.logout()
  }
}

}
</script>
