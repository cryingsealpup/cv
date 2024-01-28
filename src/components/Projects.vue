<script setup>
import { ref, computed } from 'vue'

const filter = ref(null)

const projects = ref([
    {
        spec: 'Vue, PostCSS, Vite', 
        info: [
            {
                name: 'cv',
                desc: 'Эта страница',
                repo: '',
                img: ''
            }

        ]
    },
    {
        spec: 'Vanilla'
    },
    {
        spec: 'Pug'
    },
    {
        spec: 'SASS'
    }
])

const projectTab = computed(() => filter.value ? projects.value.filter(el => el.spec.includes(filter.value)) : projects.value)
</script>

<template>
    <div class="projects">
        <h2> Проекты </h2>
        <ul>
            <li v-for="project in projectTab">
                {{ project.spec }}
            </li>
        </ul>
    </div>
</template>