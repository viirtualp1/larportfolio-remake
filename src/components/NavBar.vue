<template>
  <nav class="navbar navbar-expand-lg bg-dark">
    <div class="container-fluid">
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbar-menu"
        aria-controls="navbar-menu"
        aria-expanded="false"
        aria-label="Переключатель навигации"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbar-menu">
        <a class="navbar-brand" href="#">
          <img :src="larLogo" alt="lar-logo" class="lar-logo" />
        </a>

        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#about-lar">Главная</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#members">Участники</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#projects">Проекты</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
nav {
  .lar-logo {
    width: 45px;
    border-radius: 50%;
  }

  ul > li {
    a {
      font-size: 1.1rem;
      color: rgb(209, 208, 208);

      &:hover {
        cursor: pointer;
        color: #fff;
      }
    }

    .active {
      color: #fff !important;
      cursor: default !important;
    }
  }
}
</style>

<script>
export default {
  data() {
    return {
      larLogo:
        "https://i.ibb.co/Ss12Gjb/Ebzlau8-Ja8l-Hz8-Qu-Yf-Ispq-Ehru-s-LAVItm73-CF5-UVk-PWm-P9-Wbp768py-BTv-S4b-Gvb-MTHv805i-STqdu1-SWJY.jpg",
    };
  },
};
</script>
