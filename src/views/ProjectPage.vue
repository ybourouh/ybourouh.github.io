<template>
  <div class="project-page" v-if="project">
    <a href="#" class="back-link" @click.prevent="goBack">← Back to projects</a>

    <div class="project-header" :style="{ 'border-color': project.accentColor }">
      <h1>{{ project.name }}</h1>
    </div>

    <div class="project-content" v-html="project.htmlDescription"></div>
  </div>

  <div v-else class="project-page">
    <p>Project not found.</p>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import gameProjectsData from "@/data/GameProjectsData.ts";
import otherProjectsData from "@/data/OtherProjectsData.ts";

export default Vue.extend({
  name: "ProjectPage",
  data: function () {
    return {
      project: null as any,
    };
  },
  created: function () {
    this.project = this.findProject(this.$route.params.id);
  },
  watch: {
    "$route.params.id": function () {
      this.project = this.findProject(this.$route.params.id);
    },
  },
  methods: {
    findProject: function (id: string) {
      const allProjects = [...gameProjectsData, ...otherProjectsData];
      return allProjects.find((item: any) => item.id === id) || null;
    },
    goBack: function () {
      this.$router.go(-1);
    },
  },
});
</script>

<style scoped>
.project-page {
  max-width: 900px;
}

.back-link {
  display: inline-block;
  margin-bottom: 20px;
  opacity: 0.8;
}

.back-link:hover {
  opacity: 1;
}

.project-header {
  border-left: 6px solid;
  padding-left: 16px;
  margin-bottom: 24px;
}

.project-header h1 {
  margin: 0;
  margin-bottom: 0;
}

.project-content {
  line-height: 1.8;
}
</style>
