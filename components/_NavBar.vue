<script>
export default {
  data() {
    return {
      light: false,
    }
  },
  methods: {
    toggle() {
      // alert(Object.keys(this.$data)
      this.$data.light = !this.$data.light // light = !light
    },
  },
}
</script>

<template>
  <div>
    <b-navbar toggleable="lg" :type='light ? "light" :"dark"' :variant='light ? "light" :"dark"'>
      <b-navbar-brand href="/"
        ><img src="icon.png" alt="logo" style="width: 30px" /> Arda
        Gürcan</b-navbar-brand
      >

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="/">Home</b-nav-item>
          <b-nav-item href="/projects">Projects</b-nav-item>
          <b-nav-item href="/about">About Me</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-form-input
              size="sm"
              class="mr-sm-2"
              placeholder="Search"
            ></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit"
              >Search</b-button 
            >
          </b-nav-form>
          
          <b-nav-item>
            <b-icon-moon-fill v-if="light" @click.prevent="toggle()"></b-icon-moon-fill>
            <b-icon-sun-fill v-else @click.prevent="toggle()"></b-icon-sun-fill>
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
