<template>
  <div>
    <h1>Next generation digital banking</h1>
    <p>
      Take your financial life online. Your Easybank account will be a
      one-stop-shop for spending, saving, budgeting, investing, and much more.
    </p>
    <button>Request Invite</button>
    <section>
      <h2>Why choose Easybank?</h2>
      <p>
        We leverage Open Banking to turn your bank account into your financial
        hub. Control your finances like never before.
      </p>
      <template v-for="advantage in advantages" :key="advantage.title">
        <h3>{{ advantage.title }}</h3>
        <p>{{ advantage.reason }}</p>
      </template>
    </section>
    <section>
      <h2>Latest Articles</h2>
      <eb-article
        v-for="article in latestArticles"
        :key="article.title"
        :article="article"
      />
    </section>
    <footer>
      <eb-footer-menu />
      © Easybank. All Rights Reserved

      <div class="attribution">
        Challenge by
        <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
          >Frontend Mentor</a
        >. Coded by <a href="https://github.com/grantmcdade">Grant McDade</a>.
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import type { Article } from '@/types';
import { ref } from 'vue';
import EbArticle from '@/components/EbArticle.vue';
import EbFooterMenu from '@/components/EbFooterMenu.vue';

const advantages = ref([
  {
    title: 'Online Banking',
    reason:
      'Our modern web and mobile applications allow you to keep track of your finances wherever you are in the world.',
  },
  {
    title: 'Simple Budgeting',
    reason:
      'See exactly where your money goes each month. Receive notifications when you’re close to hitting your limits.',
  },
  {
    title: 'Fast Onboarding',
    reason:
      'We don’t do branches. Open your account in minutes online and start taking control of your finances right away.',
  },
  {
    title: 'Open API',
    reason:
      'Manage your savings, investments, pension, and much more from one account. Tracking your money has never been easier.',
  },
]);

const latestArticles = ref<Article[]>([
  {
    author: 'By Claire Robinson',
    title: 'Receive money in any currency with no fees',
    description:
      'The world is getting smaller and we’re becoming more mobile. So why should you be forced to only receive money in a single …',
  },
  {
    author: 'By Wilson Hutton',
    title: 'Treat yourself without worrying about money',
    description:
      'Our simple budgeting feature allows you to separate out your spending and set realistic limits each month. That means you …',
  },
  {
    author: 'By Wilson Hutton',
    title: 'Take your Easybank card wherever you go',
    description:
      'We want you to enjoy your travels. This is why we don’t charge any fees on purchases while you’re abroad. We’ll even show you …',
  },
  {
    author: 'By Claire Robinson',
    title: 'Our invite-only Beta accounts are now live!',
    description:
      'After a lot of hard work by the whole team, we’re excited to launch our closed beta. It’s easy to request an invite through the site ...',
  },
]);
</script>

<style scoped></style>
