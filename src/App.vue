<script>
import axios from 'axios';
import {store} from "./store";
import ProjectCard from "./components/ProjectCard.vue";


export default {
  data () {
    return {
      projects: [],
      store
    }
  },
  components: {
    ProjectCard
  },
  mounted() {
    this.getProjects();
  },
  methods: {
    getProjects() {
      axios.get('${store.apiBaseUrl}/api/projects').then((resp) => {
        this.projects = resp.data.results;
        console.log(resp);
      })
    }
  }
}
</script>

<template>
  <div class="container">
    <h2>Project's List</h2>
    <div class="row row-cols-4 g-3">
      <div class="col" v-for="project in projects" :key="project.id">
        <ProjectCard :project="project"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
  @use "./styles/general.scss" as *;
</style>