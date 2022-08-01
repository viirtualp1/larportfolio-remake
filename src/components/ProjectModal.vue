<template>
  <div class="modal fade" :id="project.id" tabindex="-1" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content bg-dark">
        <div class="modal-header">
          <h5 class="modal-title">{{ project.name }}</h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Закрыть"
          ></button>
        </div>

        <div class="modal-body">
          <video
            v-if="project.video"
            class="project-video"
            :src="project.video"
            autoplay
            controls
          ></video>

          <div v-else id="project-imgs" class="carousel slide" data-bs-ride="true">
            <div class="carousel-inner">
              <div
                v-for="(img, index) in project.imgs"
                :key="img"
                class="carousel-item"
                v-bind:class="{ active: index === 0 }"
              >
                <img class="project-img" :src="img" :alt="project.name" />
              </div>
            </div>
            <button
              class="carousel-control-prev"
              type="button"
              data-bs-target="#project-imgs"
              data-bs-slide="prev"
            >
              <span class="carousel-control-prev-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Previous</span>
            </button>
            <button
              class="carousel-control-next"
              type="button"
              data-bs-target="#project-imgs"
              data-bs-slide="next"
            >
              <span class="carousel-control-next-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Next</span>
            </button>
          </div>

          <p>Описание: {{ project.description }}</p>
          <div class="mb-3" id="links">
            <a
              class="nav-link"
              v-bind:class="{ disabled: isLink }"
              :href="project.link"
              target="_blank"
              >Ссылка на проект {{ project.linkProject === "" ? ": В закрытом доступе" : "" }}</a
            >
            <a class="nav-link" :href="project.linkSourceCode" target="_blank"
              >Ссылка на исходный код</a
            >
          </div>

          <div id="funcs">
            <p class="mb-0">Функции:</p>
            <ul>
              <li v-for="func in project.funcs" :key="func">{{ func }}</li>
            </ul>
          </div>

          <p class="text-muted">Дата релиза: {{ project.dateRelease }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectModal",
  props: {
    project: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      isLink: this.project.link !== "",
    };
  },
};
</script>

<style lang="scss" scoped>
.disabled {
  color: grey !important;
  text-decoration: none !important;
}

.modal-content {
  text-align: left;

  .modal-body {
    .project-video,
    .project-img {
      width: 100%;
    }

    a {
      color: rgb(102, 102, 252);
      text-decoration: underline;
    }
  }
}
</style>
