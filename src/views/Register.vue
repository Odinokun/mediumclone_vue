<template>
  <div class="auth-page">
    <div class="container page">
      <div class="row">
        <div class="col-md-6 offset-md-3 col-xs-12">
          <h1 class="text-xs-center">Sign up</h1>
          <p class="text-xs-center">
            <router-link :to="{ name: 'login' }">Need an account?</router-link>
            <!--            <router-link :to="{name: 'register'}">Have an account?</router-link>-->
          </p>
          VALIDATION ERRORS
          <form @submit.prevent="onSubmit">
            <fieldset class="form-group">
              <input
                class="form-control form-control-lg"
                type="text"
                placeholder="Username"
              />
            </fieldset>
            <fieldset class="form-group">
              <input
                class="form-control form-control-lg"
                type="email"
                placeholder="Email"
              />
            </fieldset>
            <fieldset class="form-group">
              <input
                class="form-control form-control-lg"
                type="password"
                placeholder="Password"
              />
            </fieldset>

            <button class="btn btn-lg btn-primary pull-xs-right" type="submit">
              Sign Up
            </button>
          </form>
          <button @click="increaseCounter">increase counter</button>
          <div>{{ count }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'McvRegister',
  computed: {
    count() {
      return this.$store.state.count
    },
  },
  methods: {
    onSubmit() {
      console.log('form submitted')
    },
    increaseCounter() {
      this.$store.commit('increment')
    },
  },
}
</script>
