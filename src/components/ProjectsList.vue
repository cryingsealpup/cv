<script setup>
import { ref, computed } from 'vue'

const filter = ref(null)

const projects = ref([
    {
        spec: 'vue, postcss, vite',
        info:
        {
            name: 'cv',
            desc: 'Эта страница',
            repo: '',
            img: '/src/assets/images/dontsova.png'
        }
    },
    {
        spec: 'vanilla, sass, pug',
        info:
        {
            name: 'cv',
            desc: 'Эта страница',
            repo: '',
            img: '/src/assets/images/gallery.png'
        }
    },
    {
        spec: 'pug, sass, vanilla, webpack',
        info:
        {
            name: 'Hangman',
            desc: 'Виселица',
            repo: '',
            img: '/src/assets/images/hangman.png'
        }
    },
    {
        spec: 'sass',
        info:
        {
            name: 'Hangman',
            desc: 'Виселица',
            repo: '',
            img: '/src/assets/images/hangman.png'
        }

    }
])

const projectTab = computed(() => filter.value ? projects.value.filter(el => el.spec.includes(filter.value.toLowerCase())) : projects.value)
</script>

<template>
    <div class="projects">
        <div class="projects-wrapper">
            <h2> Проекты </h2>
            <input type="text" v-model="filter">
            <ul class="projects-list">
                <li v-for="project in projectTab">
                    <img :src="project.info.img" alt="" class="projects-image">
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
input {
    font-family: "Inter", sans-serif;
    width: 20rem;
    height: 2rem;
    background: white;
    border: none;
    outline: 3px dashed black;
    box-sizing: border-box;
    color: black;
    border-radius: 0;
    padding: 0.2rem 1rem;
    transition: all 0.1s ease;
    margin-bottom: 0.8rem;
    caret-color: gray;
}

input:focus,
input:focus-visible {
    box-shadow: 0 0 15px 0rem black;
    background: black;
    border-radius: 0;
    color: white;
    border: none;
    outline: 2px dashed black;
    font-weight: 600;
}
</style>