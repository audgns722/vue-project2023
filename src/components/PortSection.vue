<script setup>
import { portText } from "@/constants/index"
</script>

<template>
    <section id="port">
        <div class="port__inner">
            <div class="port__title">
                portfolio <em>포폴 작업물</em>
            </div>
            <div class="port__wrap">
                <div :class="['port__item', 'p' + (key + 1)]" v-for="(port, key) in portText" :key="key">
                    <span class="num">{{ port.num }}</span>
                    <a href="#">
                        <img :src="port.img" alt="포트폴리오이미지1">
                    </a>
                    <h3 class="title">{{ port.title }}</h3>
                    <p class="desc">
                        {{ port.desc }}
                    </p>
                    <a class="link" :href="port.code">코드보기</a>
                    <a class="link" :href="port.view">사이트보기</a>
                </div>
            </div>
        </div>
    </section>
    <!-- //port -->
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted: function () {
        this.scrollAnimation();
    },
    methods: {
        scrollAnimation() {
            const horSection = gsap.utils.toArray(".port__item");

            gsap.to(horSection, {
                xPercent: -120 * (horSection.length - 1),
                ease: "none",
                scrollTrigger: {
                    trigger: "#port",
                    start: "top 56px",
                    end: "+=3000",
                    pin: true,
                    scrub: 1,
                    invalidateOnRefresh: true,
                    anticipatePin: 1,
                }
            });
        }
    }
}
</script>

<style lang="scss">
#port {
    width: 100%;
    overflow: hidden;
}

.port__inner {
    padding: 16px;
}

.port__title {
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
    margin-bottom: 1vw;
}

.port__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 500;
    display: inline-block;
}

.port__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;
}

.port__item {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    width: 500px;
    height: 70vh;
    background-color: #ccc;
    margin-right: 20px;
    padding: 50px 30px;
    position: relative;
    border-radius: 0 15px 15px 0;
    color: var(--white);
}

.port__item .num {
    display: block;
    position: absolute;
    font-size: 3.5rem;
    font-weight: 500;
    color: var(--mainFont-color);
    line-height: 1;
    font-family: var(--mainNum-font);
    padding-top: 10px;
    left: 30px;
    top: 15px;
    z-index: 1;
}

.port__item img {
    background-color: #122531;
    width: 100%;
    height: 250px;
    transition: all 0.3s;
    padding: 20px;
}

.port__item img:hover {
    transform: scale(1.05);
}

.port__item .title {
    text-align: center;
    font-size: 1.5rem;
    font-family: var(--mainKor-font);
    font-weight: 700;
    margin: 1vw 0;
    border-bottom: 5px solid #21313b;
    padding: 0 15px;
    line-height: 1;
}

.port__item .desc {
    font-family: var(--mainKor-font);
    font-size: 1.2rem;
    margin: 15px 0;
    text-align: justify;
}

.port__item .link {
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid var(--subBg500);
    width: 100%;
    height: 50px;
    transition: all 0.3s;
}

.port__item .link:hover {
    background-color: var(--subBg500);
    color: var(--mainFont-color);
}

.port__item.p1 {
    background-color: #0a1e2e;
}

.port__item.p2 {
    background-color: #424951;
}

.port__item.p3 {
    background-color: #5b6c7d;
    color: var(--black);
    ;
}

.port__item.p4 {
    background-color: #80969d;
    color: var(--black);
}

.port__item.p5 {
    background-color: #b7bec2;
    color: var(--black);
}

.port__item.p6 {
    background-color: #9aaabb;
}

.port__item.p7 {
    background-color: #8fa4bb;
}

.port__item.p8 {
    background-color: #7e9cbb;
}

.port__item.p9 {
    background-color: #6b849e;
}

.port__item.p10 {
    background-color: #596d83;
}
</style>