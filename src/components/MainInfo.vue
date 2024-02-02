<script setup>
import { ref } from 'vue'
</script>
<template>
    <header class="header">
        <div class="header__wrapper" v-motion-pop-visible>
            <h1 class="header__title">
                Екатерина Радченко
            </h1>
            <ul class="header__more-info">
                <li>
                    Frontend-разработчик
                </li>
            </ul>
            <a href="#about">
                <div class="header__see-more">
                    <p class="more">
                        Больше
                    </p>
                </div>
            </a>
        </div>
    </header>
</template>