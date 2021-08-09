<template>
<div>
    <Menu />
  <div class="container-fluid mt-5">
    <div class="row">
      <div class="col-md-6 offset-md-3">
        <div class="card text-center">
          <div class="card-header">Registration Page</div>
          <div class="card-body">
            <form @submit.prevent="registerUser">

              <div class="mb-3 row">
                <label for="email" class="col-sm-2 col-form-label">Name</label>
                <div class="col-sm-10">
                  <input type="text" class="form-control" id="name" v-model="registerForm.name">
                </div>
              </div>
              <div class="mb-3 row">
                <label for="email" class="col-sm-2 col-form-label">Email</label>
                <div class="col-sm-10">
                  <input type="email" class="form-control" id="email" v-model="registerForm.email">
                </div>
              </div>
              <div class="mb-3 row">
                <label for="inputPassword" class="col-sm-2 col-form-label">Password</label>
                <div class="col-sm-10">
                  <input type="password" class="form-control" id="inputPassword" v-model="registerForm.password">
                </div>
              </div>
              <button type="sumbit" class="btn btn-outline-primary">Submit</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>
<script>
export default {
  auth: 'guest',
  data() {
    return {
      registerForm: {
        name: '',
        email: '',
        password: ''
      }
    }
  },
  methods: {
    async registerUser() {
      try {
      const data= await this.$axios.$post('/auth/register',this.registerForm)
      this.$auth.setUserToken(data.access_token);

        console.log(data.access_token);
      } catch (err) {
        console.log(err)
      }
    }
  }
}
</script>
