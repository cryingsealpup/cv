<script setup>
import { ref } from 'vue'

const skills = ref({
    'Языки': [ 'HTML', 'CSS', 'JavaScript', 'TypeScript', 'PHP' ],
    'Фреймворки': [ 'VueJs', 'React' ], 
    'Шаблонизаторы': [ 'Twig', 'Pug' ], 
    'Контроль версий': [ 'Git' ], 
    'Прочее': [ 'SASS', 'PostCSS', 'Docker', 'Node.js', 'Drupal' ]
})
</script>
<template>
    <div class="stack" id="skills">
        <div class="skills" v-for="(list, name, index) in skills" :key="index">
            <h2 v-motion-roll-visible-top> {{ name }} </h2>
            <ul class="stack-list" v-motion-roll-visible-top>
                <li v-for="skill in list" :key="skill.id">
                    {{ skill }}
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
@media (max-width: 48em) {
    h2 {
        font-size: 1.1rem;
    }
}
</style>