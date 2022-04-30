<script>
export default {
  data() {
    return {
      light: false,
    }
  },
  methods: {
    toggle() {
      this.$data.light = !this.$data.light
    },
  },
}
</script>
<template>
  <div class="fixed">
    <b-navbar
      toggleable="lg"
      :type="light ? 'light' : 'dark'"
      :variant="light ? 'light' : 'dark'"
    >
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

          <b-nav-item @click.prevent="toggle()">
            <b-icon-moon-fill v-if="light"></b-icon-moon-fill>
            <b-icon-sun-fill v-else></b-icon-sun-fill>
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <svg id="drip" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path
        :fill="`var(--${light ? 'light' : 'gray-dark'})`"
        fill-opacity="1"
        d="M0,256L7.1,256C14.1,256,28,256,42,245.3C56.5,235,71,213,85,192C98.8,171,113,149,127,165.3C141.2,181,155,235,169,261.3C183.5,288,198,288,212,250.7C225.9,213,240,139,254,90.7C268.2,43,282,21,296,32C310.6,43,325,85,339,96C352.9,107,367,85,381,64C395.3,43,409,21,424,37.3C437.6,53,452,107,466,128C480,149,494,139,508,160C522.4,181,536,235,551,240C564.7,245,579,203,593,197.3C607.1,192,621,224,635,202.7C649.4,181,664,107,678,80C691.8,53,706,75,720,101.3C734.1,128,748,160,762,149.3C776.5,139,791,85,805,85.3C818.8,85,833,139,847,154.7C861.2,171,875,149,889,128C903.5,107,918,85,932,106.7C945.9,128,960,192,974,213.3C988.2,235,1002,213,1016,192C1030.6,171,1045,149,1059,165.3C1072.9,181,1087,235,1101,256C1115.3,277,1129,267,1144,234.7C1157.6,203,1172,149,1186,106.7C1200,64,1214,32,1228,21.3C1242.4,11,1256,21,1271,64C1284.7,107,1299,181,1313,192C1327.1,203,1341,149,1355,117.3C1369.4,85,1384,75,1398,101.3C1411.8,128,1426,192,1433,224L1440,256L1440,0L1432.9,0C1425.9,0,1412,0,1398,0C1383.5,0,1369,0,1355,0C1341.2,0,1327,0,1313,0C1298.8,0,1285,0,1271,0C1256.5,0,1242,0,1228,0C1214.1,0,1200,0,1186,0C1171.8,0,1158,0,1144,0C1129.4,0,1115,0,1101,0C1087.1,0,1073,0,1059,0C1044.7,0,1031,0,1016,0C1002.4,0,988,0,974,0C960,0,946,0,932,0C917.6,0,904,0,889,0C875.3,0,861,0,847,0C832.9,0,819,0,805,0C790.6,0,776,0,762,0C748.2,0,734,0,720,0C705.9,0,692,0,678,0C663.5,0,649,0,635,0C621.2,0,607,0,593,0C578.8,0,565,0,551,0C536.5,0,522,0,508,0C494.1,0,480,0,466,0C451.8,0,438,0,424,0C409.4,0,395,0,381,0C367.1,0,353,0,339,0C324.7,0,311,0,296,0C282.4,0,268,0,254,0C240,0,226,0,212,0C197.6,0,184,0,169,0C155.3,0,141,0,127,0C112.9,0,99,0,85,0C70.6,0,56,0,42,0C28.2,0,14,0,7,0L0,0Z"
      ></path>
    </svg>
  </div>
</template>
<style scoped>
.fixed {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999;
  width: 100%;
  pointer-events: none;
}

.b-icon {
  float: right;
  margin: 1rem;
  margin-top: 0.375rem;
}

.navbar {
  pointer-events: all;
}

svg#drip {
  transform-origin: 0 0;
  transform: scale(1.2, 0.05) translateY(-1px);
  pointer-events: all;
}
</style>
