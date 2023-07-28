<template>
  <h1>{{ title }}</h1>
  <p>Welcome..</p>
  <teleport to="#modals" v-if="showModal">
    <modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab yours now!</p>
    </modal>
  </teleport>
  <!--<input type="text" ref="name">
  <button @click="handleClick">click me</button>-->

  <teleport to='#modals' v-if="showModalTwo">
    <modal @close="toggleModalTwo">
      <h1>Sign up to the newsletter</h1>
      <p>For more updates and promo codes!</p>
    </modal>
  </teleport>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal</button>
</template>


<script>
import modal from "./components/modal.vue"

export default {
  name: 'App',
  components: { modal },
  data() {
    return {
      title: 'My First Vue App',
      header: 'Sign up for the Giveaway!',
      text: 'Kasabot na gamay',
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }


  //methods: {
  // handleClick() {
  // console.log(this.$refs.name)
  // this.$refs.name.classList.add('active')
  // this.$refs.name.focus()
  //}

}
</script>

<style>
#app,
#modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
