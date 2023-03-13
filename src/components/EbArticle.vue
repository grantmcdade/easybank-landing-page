<template>
    <div>
        <img :src="article.image" />
        <div class="text-left">
            <span class="author">{{ article.author }}</span>
        </div>
        <h3>{{ article.title }}</h3>
        <p class="text-green">{{ article.description }}</p>
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
    opacity: 0.5;
    height: 12.5rem;
    width: 20.5rem;
    margin-top: 0.5rem;
}

.author {
    display: inline-block;
    font-size: 0.6rem;
    margin-top: 1.5rem;
    margin-left: 3.5rem;
    text-align: left;
}

h3 {
    margin-top: 0.535rem;
    margin-left: 3.45rem;
    margin-right: 3.45rem;
    letter-spacing: normal;
    text-align: left;
    font-size: 0.96rem;
    line-height: 1.3;
}

p {
    margin-left: 2.2rem;
    margin-right: 2.2rem;
    line-height: 1.4;
    text-align: left;
    font-size: 0.75rem;
}
</style>
