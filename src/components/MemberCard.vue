<template>
  <div class="card bg-dark text-white member-card">
    <img :src="member.imgSrc" alt="member-img" class="member-avatar" />

    <div class="card-body">
      <h5 class="card-title">{{ member.name }}</h5>

      <p class="card-text">{{ member.profType }}</p>
    </div>

    <ul class="list-group list-group-flush">
      <li class="list-group-item bg-dark" v-for="link in member.links" :key="link.name">
        <a :href="link.href" target="_blank">
          <img :src="logoLinks[`${link.name.toLowerCase()}`]" alt="link-logo" class="link-logo" />

          {{ link.name }}</a
        >
      </li>
    </ul>

    <div class="card-footer">
      <p class="text-muted">
        {{ member.type === "Основатель" ? member.type : `Дата вступления: ${member.dateEntry}` }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "MemberCard",
  props: {
    member: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      logoLinks: {
        youtube:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/YouTube_full-color_icon_%282017%29.svg/2560px-YouTube_full-color_icon_%282017%29.svg.png",
        vkontakte:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/VK_Compact_Logo.svg/2048px-VK_Compact_Logo.svg.png",
        github: "https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png",
      },
    };
  },
};
</script>

<style scoped lang="scss">
.member-card {
  width: 18rem;
  margin: 1rem;

  .member-avatar {
    width: 250px;
    margin: 1rem 0.5rem 0 0.3rem;
    border-radius: 15px;
    box-shadow: 1px 2px 5px #000;
  }

  ul > li {
    a {
      text-decoration: none;
    }

    img {
      width: 20px;
      border-radius: 0;
      margin: 0;
    }
  }

  .card-footer > p {
    margin-bottom: 0;
  }
}
</style>
