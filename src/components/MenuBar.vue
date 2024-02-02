<script setup>
import { ref } from 'vue'

const menu = ref([
    {
        link: '#about',
        text: 'Обо мне'
    },
    {
        link: '#skills',
        text: 'Навыки'
    },
    {
        link: '#projects',
        text: 'Проекты'
    },
    {
        link: '#contacts',
        text: 'Контакты'
    },
])

</script>
<template>
    <div class="menu">
        <nav class="menu__links" v-motion-slide-visible-top>
            <ul>
                <li class="menu__item" v-for="item in menu"> <a :href="item.link">{{item.text}}</a> </li>
            </ul>
        </nav>
    </div>
</template>