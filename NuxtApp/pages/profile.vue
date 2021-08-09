<template>
  <div>
    <Menu />
    <div class="container-fluid mt-5">
      <div class="row">
        <div class="col-md-6 offset-md-3">
          <div class="card">

            <div class="card-body">
              <h5 v-if="loggdIn" class="card-title text-center">{{user.name}}</h5>
              <p
                class="card-text"
              >Some quick example text to build on the card title and make up the bulk of the card's content.</p>
            </div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item">An item</li>
              <li class="list-group-item">A second item</li>
              <li class="list-group-item">A third item</li>
            </ul>
            <div class="card-body">
              <a href="#" class="card-link">Card link</a>
              <a href="#" class="card-link">Another link</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
   middleware: 'auth',

   computed:{
     loggdIn(){
       return this.$store.state.auth.loggedIn;
     },
     user(){
       return this.$store.state.auth.user;
     }
   }

}
</script>
