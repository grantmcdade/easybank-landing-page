<template>
  <div>
    <div class="author">{{ article.author }}</div>
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

<style scoped></style>
