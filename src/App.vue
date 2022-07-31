<template>
  <div id="app">
    <NavBar />

    <div class="container-sm">
      <div id="about-lar">
        <AboutLAR class="mt-3" :mainInfo="mainInfo" />
      </div>

      <div id="member">
        <h3 class="text-white mt-3">Участники</h3>

        <div class="row justify-content-md-center mb-3">
          <MemberCard v-for="member in members" :member="member" :key="member.name" />
        </div>
      </div>

      <div id="projects">
        <h3 class="text-white">Проекты</h3>

        <ProjectLAR v-for="project in projects" :project="project" :key="project.name">
          <ProjectModal :project="project" />
        </ProjectLAR>
      </div>
    </div>
  </div>
</template>

<script>
import AboutLAR from "@/components/AboutLAR.vue";
import NavBar from "@/components/NavBar.vue";
import MemberCard from "@/components/MemberCard.vue";
import ProjectLAR from "@/components/ProjectLAR.vue";
import ProjectModal from "@/components/ProjectModal.vue";

export default {
  name: "App",
  components: {
    MemberCard,
    NavBar,
    AboutLAR,
    ProjectLAR,
    ProjectModal,
  },

  data() {
    return {
      mainInfo: {
        dateFounding: "20 августа 2018",
        description: "Это инди-компания, которая разрабатывает веб-приложения и игры.",
      },

      members: [
        {
          name: "Никита Зинин",
          type: "Основатель",
          dateEntry: "2020",
          profType: "Junior Front-End Vue Developer",
          imgSrc: "https://i.ibb.co/GV8Rmgx/nikita.jpg",
          links: [
            {
              name: "YouTube",
              href: "https://www.youtube.com/channel/UCeh4yaV7iYy0zrbN1-qy2IQ",
            },
            {
              name: "Github",
              href: "https://github.com/viirtualp1",
            },
            {
              name: "Vkontakte",
              href: "https://vk.com/virtualp1",
            },
          ],
        },
        {
          name: "Данил Чернышев",
          type: "Основатель",
          profType: "Junior Back-End Node.JS Developer",
          dateEntry: "2020",
          imgSrc:
            "https://i.ibb.co/1dmRcXm/Pf-ENxv-UXMowl-Mi5r-KXLb-U6-T9-Igf-Xfgr-KY7-xk-S4b3-59weq3h-YJr-Ckxq-g-ZSs6fiy3lg4-Q.jpg",
          links: [
            {
              name: "YouTube",
              href: "https://www.youtube.com/c/Degfer",
            },
            {
              name: "Github",
              href: "https://github.com/Degfer",
            },
            {
              name: "Vkontakte",
              href: "https://vk.com/23tvrus",
            },
          ],
        },
      ],

      projects: [
        {
          name: "LARSN",
          video: "/media/LARSN.e9e276ed.mp4",
          id: "larsn",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  background: rgb(41, 41, 41);
}
</style>
