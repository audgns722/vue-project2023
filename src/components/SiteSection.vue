<script setup>
import { siteText } from "@/constants/index"
</script>

<template>
    <section id="site">
        <div class="site__inner">
            <div class="site__title">
                Site Coding <em>나의 작업물</em>
            </div>
            <div class="site__wrap">
                <div :class="['site__item', 's' + (key + 1)]" v-for="(site, key) in siteText" :key="key">
                    <span class="num">{{ key + 1 }}</span>
                    <div class="text">
                        <div>{{ site.text[0] }}</div>
                        <div>{{ site.text[1] }}</div>
                        <div>{{ site.text[2] }}</div>
                    </div>
                    <h3 class="title">
                        {{ site.title }}
                    </h3>
                    <div class="btn">
                        <a :href="site.code">code</a>
                        <a :href="site.view">view</a>
                    </div>
                    <div class="info">
                        <span>{{ site.info[0] }}</span>
                        <span>{{ site.info[1] }}</span>
                        <span>{{ site.info[2] }}</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <!-- //site -->
</template>

<style lang="scss">
.site__inner {
    padding: 16px;
}

.site__title {
    position: sticky;
    top: 70px;
    left: 0;
    width: 48%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 700;
    line-height: 1.6;
    text-transform: uppercase;
    font-family: var(--mainEng-font);
    color: var(--mainFont-color);
    border-bottom: 5px solid var(--subBg500);
}

.site__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 500;
    display: inline-block;
}

.site__wrap {
    display: flex;
    flex-direction: column;
    width: 100%;
}

.site__item {
    background-color: var(--subBg200);
    padding: 3vw;
    text-align: center;
    position: relative;
    border-radius: 0 0 15px 15px;
    margin-bottom: 2vw;
    margin-top: 1vw;
    color: var(--mainFont-color);
    position: sticky;
    left: 0;
}

.site__item.s1 {
    background-color: #616c79;
    top: 180px;
}

.site__item.s2 {
    background-color: #4a525c;
    top: 200px
}

.site__item.s3 {
    background-color: #333941;
    top: 220px;
}

.site__item.s4 {
    background-color: #21252b;
    top: 240px;
}

.site__item .num {
    display: block;
    font-size: 5vw;
    font-weight: 700;
    color: var(--mainFont-color);
    line-height: 1;
    font-family: var(--mainNum-font);
    padding-top: 10px;
    text-align-last: left;
    position: absolute;
    left: 30px;
    top: 15px;
}

.site__item .text {
    font-size: 3vw;
    text-transform: uppercase;
    line-height: 1.3;
    font-family: var(--mainEng-font);
    font-weight: 700;
    margin-top: 3vw;
    margin-bottom: 4vw;
    letter-spacing: 0.7vw;
}

.site__item .title {
    padding-bottom: 1vw;
    font-size: 1.5vw;
    font-family: var(--mainKor-font);
    font-weight: 500;
    letter-spacing: 1vw;
    display: inline-block;
    border-bottom: 5px solid var(--subBg200);
    margin-bottom: 3vw;
}

.site__item .btn a {
    display: inline-block;
    font-size: 1.5vw;
    padding: 10px 20px;
    background-color: var(--subBg200);
    color: var(--black);
    border-radius: 15px;
    transition: all 0.3s;
    font-weight: 700;
    margin-bottom: 2vw;
}

.site__item .btn a:hover {
    background-color: var(--subBg400);
    color: var(--mainFont-color);
}

.site__item .info {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    font-size: 1nvw;
    font-family: var(--mainEng-font);
    text-transform: uppercase;
    font-weight: 500;
    color: var(--white100);
}

.site__item .info span em {
    font-size: 1.3vw;
    font-weight: 500;
    color: var(--mainFont-color);
}</style>