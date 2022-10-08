<template>
  <div>
    <navbar />
    <section class="about">
      <h1 class="heading">about <span>me</span></h1>

      <div class="row">
        <div class="info-container">
          <h1>personal info</h1>

          <div class="box-container">
            <div class="box">
              <h3><span>name : </span> {{ name }}</h3>
              <h3><span>age : </span> {{ age }}</h3>
              <h3><span>email : </span> {{ email }}</h3>
              <h3><span>address : </span> {{ address }}</h3>
            </div>

            <div class="box">
              <h3><span>freelance : </span> available</h3>
              <h3><span>skill : </span> -</h3>
              <h3><span>experience : </span> 4 years</h3>
              <h3><span>language : </span> thai</h3>
            </div>
          </div>

          <a href="/profilewithcss/files/resume.pdf" class="btn">
            download CV <i class="fas fa-download"></i>
          </a>
        </div>

        <div class="count-container">
          <div class="box">
            <h3>5+</h3>
            <p>years of experience</p>
          </div>

          <div class="box">
            <h3>10+</h3>
            <p>happy clients</p>
          </div>

          <div class="box">
            <h3>20+</h3>
            <p>project completed</p>
          </div>

          <div class="box">
            <h3>5+</h3>
            <p>Certificates</p>
          </div>
        </div>
      </div>
    </section>

    <!-- about section ends -->

    <!-- skills section starts  -->

    <section class="skills">
      <h1 class="heading"><span>my</span> skills</h1>

      <div class="box-container">
        <div class="box">
          <img src="images/icon-1.png" />
          <h3>html</h3>
        </div>
        <div class="box">
          <img src="images/icon-2.png" />
          <h3>css</h3>
        </div>
        <div class="box">
          <img src="images/icon-3.png" />
          <h3>javascript</h3>
        </div>
        <div class="box">
          <img src="images/icon-4.png" />
          <h3>sass</h3>
        </div>
        <div class="box">
          <img src="images/icon-5.png" />
          <h3>angular</h3>
        </div>
        <div class="box">
          <img src="images/icon-6.png" />
          <h3>react.js</h3>
        </div>
      </div>
    </section>
    <!-- about section ends -->
  </div>
</template>
<script>
import Navbar from "../components/Navbar.vue";
import axios from "axios";

export default {
  components: { Navbar },
  methods: {
    async FetchExperience() {
      try {
        let res = await axios.get(
          "https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/experiences"
        );
        this.experiences = res.data;
      } catch (error) {}
    },
    async fetchskill() {
      try {
        let res = await axios.get(
          "https://633fc566e44b83bc73c0f545.mockapi.io/profile/v1/skills"
        );
        this.skill = res.data;
      } catch (error) {}
    },
  },
  data() {
    return {
      name: "Phuet Phongkheaw",
      age: "20",
      email: "Phuetphongkheaw@gmail.com",
      address: "Pathumtani Thailand 12120",
      experiences: [],
      skill: [],
    };
  },
  beforeMount() {
    this.FetchExperience();
    this.fetchskill();
  },
};
</script>

<style>
</style>