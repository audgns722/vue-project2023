<script setup>
import { skillText } from "@/constants/index"
</script>

<template>
    <section id="skill">
        <div class="skill__inner">
            <h2 class="skill__title">challenge <em>나의 도전</em></h2>
            <div class="skill__desc">
                <div v-for="(skill, key) in skillText" :key="key">
                    <span>{{ key + 1 }}</span>
                    <h3>{{ skill.title }}</h3>
                    <p>{{ skill.desc }}</p>
                </div>
            </div>
        </div>
    </section>
    <!-- //skill -->
</template>

<style lang="scss">
.skill__inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;
}

.skill__title {
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

.skill__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 500;
    display: inline-block;
}

.skill__desc {
    width: 50%;
}

.skill__desc .text {}

.skill__desc span {
    display: block;
    font-size: 5vw;
    font-weight: 700;
    color: var(--subBg200);
    line-height: 1;
    font-family: var(--mainNum-font);
    padding-top: 10px;
}

.skill__desc h3 {
    margin-left: 3vw;
    display: inline-block;
    font-size: 2vw;
    color: var(--white100);
    border-bottom: 3px dashed var(--subBg100);

}

.skill__desc p {
    font-size: 2vw;
    color: var(--mainFont-color);
    margin-left: 3vw;
    margin-top: 2vw;
    margin-bottom: 30vw;

}

@media(max-width:800px) {
    .skill__inner {
        flex-direction: column;
    }

    .skill__title {
        width: 100%;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--mainBg-color);
        text-align: center;
    }

    .skill__desc {
        width: 100%;
        padding: 0 5vw;
    }

    .skill__desc span {
        font-size: 15vw;
        padding-top: 0;
    }

    .skill__desc h3 {
        font-size: 4vw;
        margin-left: 10vw;
    }

    .skill__desc p {
        font-size: 2.5vw;
        margin-left: 10vw;
    }
}
</style>