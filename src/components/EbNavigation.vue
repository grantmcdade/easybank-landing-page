<template>
    <div>
        <nav class="nav">
            <div class="flex-container">
                <img src="@/assets/images/logo.svg" alt="" />
                <img
                    v-if="!showMenu"
                    src="@/assets/images/icon-hamburger.svg"
                    alt=""
                    @click="showMenu = true"
                />
                <img
                    v-if="showMenu"
                    class="hamburger"
                    src="@/assets/images/icon-close.svg"
                    alt=""
                    @click="showMenu = false"
                />
                <div v-if="showMenu" class="overlay" @click="showMenu = false">
                    <ul
                        :class="{
                            'menu-items': showMenu,
                            'menu-hide': !showMenu,
                        }"
                    >
                        <li class="menu-start">Home</li>
                        <li>About</li>
                        <li>Contact</li>
                        <li>Blog</li>
                        <li class="menu-end">Careers</li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const showMenu = ref(true);
</script>

<style lang="scss" scoped>
.nav {
    .flex-container {
        display: flex;
        justify-content: space-between;

        @media (min-width: 375px) {
            align-items: stretch;
        }
    }

    img {
        margin: 1.5rem;
    }

    .hamburger {
        @media (min-width: 375px) {
            display: none;
        }
    }

    .menu-hide {
        display: none;
    }

    .menu-items {
        position: absolute;
        background-color: var(--clr-white);
        list-style-type: none;
        margin: 0;
        padding: 0;
        top: 10vh;
        left: 10vw;
        right: 10vw;

        li {
            background-color: var(--clr-white);
            width: 70vw;
            text-align: center;
            font-size: 14px;
            padding: 0.8em;
        }

        @media (min-width: 375px) {
            position: inherit;
            display: flex;
            align-items: stretch;
            justify-content: space-around;
        }
    }

    .overlay {
        position: fixed; /* Sit on top of the page content */
        // display: none; /* Hidden by default */
        width: 100%; /* Full width (cover the whole page) */
        height: 100%; /* Full height (cover the whole page) */
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(
            0,
            0,
            0,
            0.5
        ); /* Black background with opacity */
        z-index: 2; /* Specify a stack order in case you're using a different order for other elements */
        cursor: pointer; /* Add a pointer on hover */

        @media (min-width: 375px) {
            position: inherit;
            width: 50%;
            flex: 1;
        }
    }

    .menu-start {
        margin-right: auto;
    }

    .menu-end {
        margin-left: auto;
    }
}
</style>
