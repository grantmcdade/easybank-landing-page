<template>
    <div class="eb-home">
        <section class="pb-21">
            <div class="mockups"></div>
            <h1 class="mb-4">Next generation digital banking</h1>
            <p class="px-4 pb-8 my-0">
                Take your financial life online. Your Easybank account will be a
                one-stop-shop for spending, saving, budgeting, investing, and
                much more.
            </p>
            <request-invite />
        </section>
        <section class="shaded pt-12 pb-7">
            <h2 class="section-title">Why choose Easybank?</h2>
            <p class="pb-10">
                We leverage Open Banking to turn your bank account into your
                financial hub. Control your finances like never before.
            </p>
            <template v-for="advantage in advantages" :key="advantage.title">
                <img
                    class="advantage-icon"
                    :src="advantage.image"
                    v-if="advantage.image"
                    alt=""
                />
                <h3 class="advantage-title">
                    {{ advantage.title }}
                </h3>
                <p class="advantage-reason">
                    {{ advantage.reason }}
                </p>
            </template>
        </section>
        <section class="pt-16">
            <h2>Latest Articles</h2>
            <eb-article
                v-for="article in latestArticles"
                :key="article.title"
                :article="article"
            />
        </section>
        <footer>
            <eb-footer-menu />
            <request-invite />

            <div>© Easybank. All Rights Reserved</div>

            <div class="attribution">
                Challenge by
                <a
                    href="https://www.frontendmentor.io?ref=challenge"
                    target="_blank"
                    >Frontend Mentor</a
                >. Coded by
                <a href="https://github.com/grantmcdade">Grant McDade</a>.
            </div>
        </footer>
    </div>
</template>

<script setup lang="ts">
import type { Article } from '@/types';
import { ref } from 'vue';
import EbArticle from '@/components/EbArticle.vue';
import EbFooterMenu from '@/components/EbFooterMenu.vue';
import RequestInvite from '@/components/RequestInvite.vue';
import iconOnline from '@/assets/images/icon-online.svg';
import iconBudgeting from '@/assets/images/icon-budgeting.svg';
import iconOnboarding from '@/assets/images/icon-onboarding.svg';
import iconApi from '@/assets/images/icon-api.svg';
import imageCurrency from '@/assets/images/image-currency.jpg';

const advantages = ref([
    {
        image: iconOnline,
        title: 'Online Banking',
        reason: 'Our modern web and mobile applications allow you to keep track of your finances wherever you are in the world.',
    },
    {
        image: iconBudgeting,
        title: 'Simple Budgeting',
        reason: 'See exactly where your money goes each month. Receive notifications when you’re close to hitting your limits.',
    },
    {
        image: iconOnboarding,
        title: 'Fast Onboarding',
        reason: 'We don’t do branches. Open your account in minutes online and start taking control of your finances right away.',
    },
    {
        image: iconApi,
        title: 'Open API',
        reason: 'Manage your savings, investments, pension, and much more from one account. Tracking your money has never been easier.',
    },
]);

const latestArticles = ref<Article[]>([
    {
        image: imageCurrency,
        author: 'By Claire Robinson',
        title: 'Receive money in any currency with no fees',
        description:
            'The world is getting smaller and we’re becoming more mobile. So why should you be forced to only receive money in a single …',
    },
    {
        image: '',
        author: 'By Wilson Hutton',
        title: 'Treat yourself without worrying about money',
        description:
            'Our simple budgeting feature allows you to separate out your spending and set realistic limits each month. That means you …',
    },
    {
        image: '',
        author: 'By Wilson Hutton',
        title: 'Take your Easybank card wherever you go',
        description:
            'We want you to enjoy your travels. This is why we don’t charge any fees on purchases while you’re abroad. We’ll even show you …',
    },
    {
        image: '',
        author: 'By Claire Robinson',
        title: 'Our invite-only Beta accounts are now live!',
        description:
            'After a lot of hard work by the whole team, we’re excited to launch our closed beta. It’s easy to request an invite through the site ...',
    },
]);
</script>

<style lang="scss" scoped>
.mockups {
    background-image: url('@/assets/images/image-mockups.png'),
        url('@/assets/images/bg-intro-desktop.svg');
    background-repeat: no-repeat;
    background-size: 93%, 220% 170%;
    background-position: bottom 0 left 0.95em, bottom -1.75em left -6.5em;
    height: 22.5rem;
}

.section-title {
    max-width: 15rem;
    margin: 1rem auto;
}

.shaded {
    background-color: var(--clr-neutral-200);
}

.advantage-icon {
    width: 4.5rem;
    aspect-ratio: 1;
}

.advantage-title {
    padding-top: 4px;
}

.advantage-reason {
    margin-bottom: 1.9rem;
}

.eb-home {
    background-image: url('@/assets/design/mobile-design-greyscale.jpg');
    background-repeat: no-repeat;
}

h1 {
    font-size: 2.42rem;
    line-height: 1.2;
}
</style>
