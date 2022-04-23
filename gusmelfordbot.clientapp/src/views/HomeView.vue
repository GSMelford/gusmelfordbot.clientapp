<template>
  <h1>GusMelfordBot</h1>
  <Login/>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component'
import Login from '@/components/Homes/Login.vue'

@Options({
  components: {
    Login
  }
})
export default class HomeView extends Vue {}
</script>

<style>
H1 {
  font-weight: bolder;
  font-size: 400%;
  text-align: center;
  text-shadow: 6px 6px 0px rgba(0,0,0,0.2);
  color: white;
}
</style>
