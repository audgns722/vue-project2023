<template>
    <section id="intro">
        <div class="intro__inner">
            <h1 class="intro__title">Front-end Developer</h1>
            <div class="intro__lines" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="intro__text">
                <div class="text">
                    <div>It always</div>
                    <div>seems impossible</div>
                    <div>until it's done.</div>
                </div>
                <div class="img"></div>
            </div>

            <div class="intro__lines bottom" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
    <!-- //intro -->
</template>

<style lang="scss">
#intro {
    height: 100vh;
}

.intro__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    flex-direction: column;
    padding: 1vw;
}

.intro__title {
    font-size: 7vw;
    text-transform: uppercase;
    font-weight: 700;
    font-family: "Archivo Black";
    color: var(--mainFont-color);
    line-height: 1;
}

.intro__lines {
    display: block;
    width: 100%;
}

.intro__lines .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--subBg400);
    margin-bottom: 0.5vw;
}

.intro__lines .line:nth-child(1) {
    background-color: #7c8eb4;
    height: 1px;
}

.intro__lines .line:nth-child(2) {
    background-color: #7282a5;
    height: 2px;
}

.intro__lines .line:nth-child(3) {
    background-color: #677697;
    height: 3px;
}

.intro__lines .line:nth-child(4) {
    background-color: #576481;
    height: 4px;
}

.intro__lines .line:nth-child(5) {
    background-color: #55627e;
    height: 5px;
}

.intro__lines .line:nth-child(6) {
    background-color: #4b5770;
    height: 6px;
}

.intro__lines .line:nth-child(7) {
    background-color: #434d63;
    height: 7px;
}

.intro__lines.bottom {
    display: none;
}

.intro__lines.bottom .line:nth-child(7) {
    background-color: #7c8eb4;
    height: 1px;
}

.intro__lines.bottom .line:nth-child(6) {
    background-color: #7282a5;
    height: 2px;
}

.intro__lines.bottom .line:nth-child(5) {
    background-color: #677697;
    height: 3px;
}

.intro__lines.bottom .line:nth-child(4) {
    background-color: #576481;
    height: 4px;
}

.intro__lines.bottom .line:nth-child(3) {
    background-color: #55627e;
    height: 5px;
}

.intro__lines.bottom .line:nth-child(2) {
    background-color: #4b5770;
    height: 6px;
}

.intro__lines.bottom .line:nth-child(1) {
    background-color: #434d63;
    height: 7px;
    margin-top: 5px;
}

.intro__text {
    background-color: var(--subBg400);
    padding: 10vw 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.intro__text .text {
    color: var(--mainFont-color);
    font-size: 3vw;
    line-height: 1.4;
    text-decoration: 0.5px dashed underline;
    text-underline-position: under;
    text-align: center;
    /* font-family: "Archivo Black"; */
    text-transform: uppercase;
    z-index: 2;
    font-weight: 500;
}

.intro__text .img {
    background-image: url(../assets/img/introtextBg01.png);
    filter: brightness(0.4);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    width: 20vw;
    height: 20vw;
    position: absolute;
    z-index: 1;
    transition: all 0.4s;
}

.intro__text:hover {
    background-color: var(--subBg500);
}

.intro__text:hover .text {
    z-index: -1;
}

.intro__text:hover .img {
    filter: brightness(1.1);
    z-index: 2;
    transform: scale(1.2);
}

.intro__text .img:hover {}

.intro__text .img:hover+.text {}

@media (max-width:800px) {
    .intro__inner {
        justify-content: center;
    }

    .intro__lines.bottom {
        display: block;
    }

    .intro__text .text {
        font-size: 2rem;
    }

    .intro__text .img {
        width: 270px;
        height: 270px;
        filter: brightness(0.8);
    }
}
</style>