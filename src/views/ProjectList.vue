<template>
  <div class="wrapper grid">
    <Project v-for="project in projects" :key="project.id" :project="project" />
  </div>
</template>
<script>
import Project from "@/components/Project.vue";
import projects from "@/data/projects.js"; // 引入專案資料

export default {
  components: {
    Project
  },
  data() {
    return {
      projects, // 直接使用從 data 檔案匯入的專案資料
    };
  },
};
</script>
