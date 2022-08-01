<template>
  <div class="card bg-dark text-white">
    <video v-if="project.video" :src="project.video" autoplay />
    <img v-else :src="project.imgs[0]" alt="test" />

    <div class="card-img-overlay">
      <button class="btn card-title project-name" @click="openModal()">
        {{ project.name }}
      </button>
    </div>

    <slot></slot>
  </div>
</template>

<script>
import bootstrap from "bootstrap/dist/js/bootstrap";

export default {
  name: "ProjectLAR",
  props: {
    project: {
      type: Object,
    },
  },

  methods: {
    openModal() {
      const myModal = new bootstrap.Modal(document.querySelector(`#${this.project.id}`));
      const modal = document.querySelector(`#${this.project.id}`);

      myModal.show(modal);
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  margin-right: 1rem;
  margin-bottom: 1rem;

  .card-img-overlay {
    text-align: left;
  }
}

.project-name {
  background: black;
  width: 80px;
  padding: 0.3rem;
  float: right;
  color: rgb(165, 165, 165);

  &:hover {
    color: #fff;
    transition: 0.3s ease;
  }
}
</style>
