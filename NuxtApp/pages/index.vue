<template>
  <div>
    <Menu />

    <section class="mt-5">
      <div class="container">
        <div class="row">
          <div class="col-md-8 offset-md-2">
            <div class="card">
              <div class="card-header">Dashboard</div>
              <div class="card-body">
               <div class="row">
                  <div class="col-4">
                    <div class="list-group" id="list-tab" role="tablist">
                      <nuxt-link class="list-group-item list-group-item-action active" id="list-home-list" data-bs-toggle="list" to="/" role="tab" aria-controls="list-home">Home</nuxt-link>
                      <nuxt-link class="list-group-item list-group-item-action" id="list-profile-list" data-bs-toggle="list" to="/profile" role="tab" aria-controls="list-profile">Profile</nuxt-link>
                      <nuxt-link class="list-group-item list-group-item-action" id="list-messages-list" data-bs-toggle="list" to="/login" role="tab" aria-controls="list-messages">Login</nuxt-link>
                      <a class="list-group-item list-group-item-action" id="list-settings-list" data-bs-toggle="list" role="tab" aria-controls="list-settings" @click.prevent="logout()">Logout</a>
                    </div>
                  </div>
                  <div class="col-8">
                    <div class="tab-content" id="nav-tabContent">
                      <p>You can activate a list group navigation without writing any JavaScript by simply specifying data-bs-toggle="list" or on an element. Use these data attributes on</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<style scoped>
@import url("https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css");
</style>
<script>
export default{
methods:{
  logout(){
    console.log("logout");
  }
}
}
</script>
