<script setup>
import { headerNav } from '@/constants/index';
</script>

<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <div class="header__logo">
                <a href="#">Hun's <em>portfolio</em><br /><i>vite.ver</i></a>
            </div>
            <nav class="header__nav" role="navigation" aria-label="메인 메뉴" :class="{ show: isNavVisible }">
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </nav>
            <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu" role="button"
                :aria-expanded="isNavVisible.toString()" @click="toggleMobileMenu">
                <span></span>
            </div>
        </div>
    </header>
    <!-- //header -->
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false,
        };
    },
    methods: {
        toggleMobileMenu() {
            this.isNavVisible = !this.isNavVisible;
        },
        scrollLink(event) {
            event.preventDefault();

            const targetId = event.target.getAttribute("href");
            const targetElement = document.querySelector(targetId);

            if (targetElement) {
                targetElement.scrollIntoView({ behavior: "smooth" });
            }
        },
    }
}
</script>

<style lang="scss">
#header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    z-index: 10000;
}

.header__inner {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    background-color: var(--subBg500);
    padding: 1rem;
}

.header__logo {
    display: flex;
}

.header__logo a {
    font-size: 1.5rem;
    color: var(--mainFont-color);
    font-weight: 500;
    text-transform: uppercase;
    text-align: center;
    line-height: 1;
}

.header__logo a:hover {
    color: var(--white100);
}

.header__logo a>em {
    color: var(--subBg200);
    font-weight: 700;
    font-size: 1.2rem;
}

.header__logo i {
    font-size: 1rem;
    text-transform: none;
}

.header__nav li {
    display: inline;
    padding: 15px 30px;
    transition: all 0.3s;
}

.header__nav li a {
    display: inline-block;
    font-size: 1.2rem;
    font-weight: 500;
    color: var(--mainFont-color);
    position: relative;
    padding-bottom: 10px;
}

.header__nav li a::before {
    content: '';
    width: 100%;
    height: 1px;
    background-color: var(--white300);
    position: absolute;
    left: 0;
    bottom: 5px;
    transform: scaleX(0);
    transition: all 0.3s;
}

.header__nav li a:hover::before {
    transform: scaleX(1);
    color: var(--white100);
}

.header__nav li a:hover {
    color: var(--white100);
}

/* header__nav__mobile */
.header__nav__mobile {
    width: 40px;
    height: 40px;
    display: none;
}

.header__nav__mobile span {
    display: block;
    width: 40px;
    height: 2px;
    background-color: var(--mainFont-color);
    margin-top: 19px;
    position: relative;
    cursor: pointer;
}

.header__nav__mobile span::before {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainFont-color);
    position: absolute;
    right: 0;
    top: 7px;
    transition: width 0.3s;
}

.header__nav__mobile span::after {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--mainFont-color);
    position: absolute;
    left: 0;
    bottom: 7px;
    transition: width 0.3s;
}

@media (max-width: 800px) {
    .header__nav {
        display: none;
    }

    .header__nav.show {
        display: block;
    }

    .header__nav.show ul {
        display: block;
        position: absolute;
        right: 0;
        top: 70px;
        background-color: #1b1b1ef1;
        z-index: 10000;
        min-width: 150px;
        padding: 20px 0;
    }

    .header__nav.show li {
        display: block;
        text-align: center;
        padding: 10px 15px;
    }

    .header__nav.show li a {
        display: inline-block;
        padding: 10px;
    }

    .header__nav.show+.header__nav__mobile span::before {
        width: 20px;
    }

    .header__nav.show+.header__nav__mobile span::after {
        width: 20px;
    }

    .header__nav__mobile {
        display: block;
    }
}
</style>