<template>
  <div class="card bg-dark text-white">
    <div class="card-body">
      <h5 class="card-title">
        <p class="lar-title">LAR STUDIO</p>
      </h5>
      <p class="card-text">
        {{ mainInfo.description }}
      </p>

      <a href="#projects" class="btn btn-primary">Проекты</a>
    </div>
    <div class="card-footer text-muted">Дата основания: {{ mainInfo.dateFounding }}</div>
  </div>
</template>

<script>
export default {
  name: "AboutLAR",
  props: {
    mainInfo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  margin: auto;
}

.lar-title {
  font: {
    weight: bold;
    size: 2rem;
  }

  text-shadow: 5px 1px 5px rgb(192, 114, 223);
  margin-bottom: 0;
}
</style>
