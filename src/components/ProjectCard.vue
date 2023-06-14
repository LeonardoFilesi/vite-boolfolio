<script>
import { store } from "../store";

export default {
    name: 'ProjectCard',
    data() {
        return {
            store
        }
    },
    props: {
        project: Object
    },
    computed: {
        contentPreview() {
            //controlla appunti Olga
        }
    }
}
</script>

<template>

        <div class="card h-90">
            <img v-if="project.image" src="${store.apiBaseUrl}/storage/${project.image}" alt="">
            <div class="card-body">
                <h5>{{ project.title }}</h5>
                <!-- <p>{{ contentPreview }}</p> -->
            </div>
        </div>
    
</template>

<style lang="scss" scoped>

</style>