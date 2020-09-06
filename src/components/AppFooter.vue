<template>
  <div class="app-footer">
    <p class="copyright">
      &#169; -<time v-once>{{ getYearNow() }}</time> ken7253
    </p>
    <div class="link-pages">
      <ul class="flex-wrp-ard">
        <li v-for="(siteData, index) in siteDatas" :key="index">
          <a :href="siteData[0]" :taget="isBlank(siteData[2])" rel="noopener">{{
            siteData[1]
          }}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      siteDatas: {
        // 0:url 1:display name 2: (target="_blank") flag
        author: ["https://dairoku-studio.com/", "Author", true],
        github: ["https://github.com/ken7253/coding_assistant", "Github", true],
      },
    };
  },
  methods: {
    getYearNow: function() {
      const getNowDate = new Date();
      return getNowDate.getFullYear();
    },
    isBlank: function(flag = false) {
      return flag ? "_blank" : "_self";
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_var.scss";
.app-footer {
  padding: 0.25rem 0 0.5rem 0;
  width: 100%;
  text-align: center;
  background-color: $color-text;
  color: $color-white;
  p {
    margin: 0;
    font-size: 0.75rem;
  }
}
.link-pages {
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    li a {
      color: $color-theme;
      font-weight: 500;
    }
  }
}
</style>
