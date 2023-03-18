<template>
    <div class="article">
        <img :src="article.image" />
        <div class="text-left">
            <span class="author">{{ article.author }}</span>
        </div>
        <h3>{{ article.title }}</h3>
        <p>{{ article.description }}</p>
    </div>
</template>

<script setup lang="ts">
import type { Article } from '@/types';

export interface Props {
    article: Article;
}

defineProps<Props>();
</script>

<style lang="scss" scoped>
img {
    max-height: auto;
    max-width: 100%;
    margin-top: 0.5rem;

    @media (min-width: 375px) {
        margin-top: 0;
    }
}

.author {
    display: inline-block;
    font-size: 0.6rem;
    margin-top: 1.5rem;
    margin-left: 3.5rem;
    text-align: left;

    @media (min-width: 375px) {
        margin: 1.5rem 0 0 1.5rem;
    }
}

h3 {
    margin-top: 0.535rem;
    margin-left: 3.45rem;
    margin-right: 3.45rem;
    letter-spacing: normal;
    text-align: left;
    font-size: 0.96rem;
    line-height: 1.3;
    margin-bottom: 0.5rem;

    @media (min-width: 375px) {
        margin: 0.5rem 1.5rem 0.5rem 1.5rem;
        padding: 0;
    }
}

p {
    margin-left: 2.35rem;
    margin-right: 2.3rem;
    margin-top: 0.55rem;
    margin-bottom: 3.5rem;
    line-height: 1.5;
    text-align: left;
    font-size: 0.75rem;

    @media (min-width: 375px) {
        margin: 0.5rem 1.5rem 0.5rem 1.5rem;
        padding: 0;
    }
}

.article {
    max-width: 16rem;
    background-color: var(--clr-neutral-100);
    border-radius: 5px;
    overflow: hidden;
}
</style>
