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
        <div class="modal-body">{{ project.description }}</div>
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
};
</script>
