<template>
  <div class="wrapper">
    <div :class="{ 'slide-scrolled': isScrolled }">
      UI/ UX Design.
      <br>
      Front-End.
      <br>
      Systems.
    </div>
  </div>
  <ProjectList />
</template>

<script>
// 引入 ProjectList 組件
import ProjectList from './ProjectList.vue';

export default {
  name: 'Home',
  components: {
    ProjectList, // 註冊 ProjectList 組件
  },
  data() {
    return {
      isScrolled: false,
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 30;  // 根據滾動高度來調整
    },
  },
};
</script>
<style lang="sass" scoped>
  @use '@/assets/styles/_mixins.sass' as *
  @use '@/assets/styles/_variables.sass' as *

  .wrapper
    div
      position: relative
      width: 100%
      color: $dark-clr
      font-size: calc($base * 10)
      font-weight: bold
      line-height: calc($base * 14)
      letter-spacing: $letterspace
      @include slideDown
      display: block

    @media (min-width: 500px) and (max-width: 1019px)
      div
          font-size: calc($base * 15)
          line-height: 110%

    @media (min-width: 1020px) 
      div
        font-size: calc($base * 25)
        line-height: 110%
</style>
