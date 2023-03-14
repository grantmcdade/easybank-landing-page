<template>
    <nav class="nav">
        <div class="flex-container">
            <img src="@/assets/images/logo.svg" alt="" />
            <img src="@/assets/images/icon-hamburger.svg" alt="" />
        </div>
        <ul class="menu-items">
            <li>Home</li>
            <li>About</li>
            <li>Contact</li>
            <li>Blog</li>
            <li>Careers</li>
        </ul>
    </nav>
</template>

<style lang="scss" scoped>
.nav {
    position: absolute;
    background-color: var(--clr-white);
    top: 0;
    left: 0;
    right: 0;
    text-align: left;

    .flex-container {
        display: flex;
        justify-content: space-between;
    }

    img {
        margin: 1.5rem;
    }

    .menu-items {
        display: none;
    }
}
</style>
