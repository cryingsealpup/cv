<script setup>
import { ref, computed } from 'vue'

const filter = ref(null)

const projects = ref([
    {
        spec: 'vue, postcss, vite, rest',
        info:
        {
            name: 'Какая ты сегодня книга Дарьи Донцовой?',
            desc: 'Выдает случайную книгу Дарьи Донцовой по клику',
            repo: 'https://github.com/cryingsealpup/agrippina',
            deploy: 'https://cryingsealpup.github.io/agrippina/',
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
            deploy: '',
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
            deploy: '',
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
            deploy: '',
            img: '/src/assets/images/hangman.png'
        }

    }
])

const projectTab = computed(() => filter.value ? projects.value.filter(el => el.spec.includes(filter.value.toLowerCase())) : projects.value)

const touched = computed(() => filter.value ? 'touched' : '')

const removeFilterValue = () => { 
    console.log(filter.value)
    filter.value = null 
    }
</script>

<template>
    <div class="projects">
        <div class="projects-wrapper">
            <h2> Проекты </h2>
            <div class="container">
                <div class="search-input">
                    <input type="text" v-model="filter" :class="touched" autocomplete="off">

                    <button type="reset" aria-label="Clear input" title="Clear input" @click.prevent="filter.value = null ">×</button>
                </div>
                </div>
                <ul class="projects-list">
                    <li v-for="project in projectTab" v-motion-slide-visible-left>
                        <img :src="project.info.img" alt="" class="projects-image">
                        <div>
                            <a href="project.info.repo"> Код </a>
                            <a href="project.info.deploy"> Деплой </a>
                        </div>
                    </li>
                </ul>
            
        </div>
    </div>
</template>

<style scoped>
.search-input {
    position: relative;
    display: inline-flex;
    align-items: center;
    flex-grow: 1;
    
}

input {
    font-family: "Inter", sans-serif;
    width: 100%;
    height: 2rem;
    background: white;
    border: none;
    outline: 3px dashed black;
    box-sizing: border-box;
    color: black;
    border-radius: 0;
    padding: 0.2rem 1rem;
    transition: all 0.1s ease;
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

button[type="submit"] {
    font-family: "Inter", sans-serif;
    font-weight: 600;
    width: fit-content;
    background: black;
    color: white;
    text-transform: uppercase;
    border: 0.3rem dotted black;
    transition: all 0.2s ease;
    padding: 0.5rem 1rem;
    margin: 0 0 0 2rem;
    cursor: pointer;
    position: relative;
}

button[type="submit"]:hover {
    transform: skewX(-10deg);
}

input.touched:focus+button[type="reset"],
input.touched:focus:hover+button[type="reset"],
input.touched:focus+button[type="reset"] {
    display: inline-flex;
}

.container {
    display: flex;
}

button[type="reset"] {
    position: absolute;
    right: 0;
    justify-content: center;
    align-items: center;
    width: 1rem;
    height: 1rem;
    appearance: none;
    border: none;
    border-radius: 50%;
    background: black;
    margin: 0 1rem;
    padding: 2px;
    color: white;
    font-size: 0.8rem;
    cursor: pointer;
    display: none;
    transition: all 0.2s ease;
}

button[type="reset"]:hover {
    background: red;
}

@media (max-width: 48em) {
    .container {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
}
</style>