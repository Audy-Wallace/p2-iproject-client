<script>
import {mapActions} from 'pinia';
import {mainStore} from '../stores/mainStore.js';
export default {
  name: "LoginView",
  data(){
      return {
          formObject: {
              email:"",
              password:"",
          }
      }
  },
  methods: {
    ...mapActions(mainStore, ["login"])
  }
};
</script>
<template>
  <div class="hero min-h-screen bg-base-200">
    <div class="hero-content flex-col">
      <div class="text-center">
        <h1 class="text-5xl font-bold">Login now!</h1>
        <p class="py-6">
          Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda
          excepturi exercitationem quasi. In deleniti eaque aut repudiandae et a
          id nisi.
        </p>
      </div>
      <div class="card flex-shrink-0 w-full max-w-sm shadow-2xl bg-base-100">
        <div class="card-body">
          <form @submit.prevent="login(formObject)">
            <div class="form-control">
              <label class="label">
                <span class="label-text">Email</span>
              </label>
              <input
                type="text"
                placeholder="email"
                class="input input-bordered"
                v-model="formObject.email"
              />
            </div>
            <div class="form-control">
              <label class="label">
                <span class="label-text">Password</span>
              </label>
              <input
                type="password"
                placeholder="password"
                class="input input-bordered"
                v-model="formObject.password"
              />
            </div>
            <div class="form-control mt-6">
              <button class="btn">Login</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
