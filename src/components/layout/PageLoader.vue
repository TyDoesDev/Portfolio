<template>
    <div id="loader" class="loader">
        <div class="logo-container">            
            <h1 style="color: white">Welcome to my site!</h1>
            <br>
            <p style="color: white">We are getting things loaded for you. ❤️</p>
        </div>
    </div>
</template>

<script>
export default {
    name:"PageLoader",
}
</script>

<style scoped lang='scss'>
    @import '@/assets/_shared.scss';
    
    .cls-1{fill:white;}
    .cls-2{fill:#efda18;}
    .cls-3{ stroke-miterlimit:10; stroke-width:0.1px;}

    .loader {
        position: fixed;
        display: flex;
        align-content: center;
        justify-content: center;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        z-index: 9000;
        background-color: $my-black;
        transition: opacity 0.3s ease-in-out;;
    }

    .bg-dark {
        background-color: $my-black;
        height: 100vh;
        width: 100%;
        position: relative;
    }

    @media screen and (orientation: portrait) {
        .logo-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            height: unset !important;
            width: 80% !important;
        }
        
        .head {

            transform: translate(5px, 39px);
            animation: head 3s ease forwards, animation,
            bounce-head 1.5s ease-in-out forwards 3.5s infinite;
        }
        .lightbulb {
            transform: translate(5px, 5px);
            animation: bounce 1.5s ease-in-out forwards 3.5s infinite;
        }

        .lightbulb-outline {
            stroke-dasharray: 56.4px;
            stroke-dashoffset: 56.4px;
            stroke: white;
            stroke-width: 0.5px;
            fill: transparent;
            animation: lightbulb 2.5s ease forwards, fill 0.5s ease forwards 2.5s;
        }

        .light {
            opacity: 0;
            animation: lights-on 0.5s ease-in forwards 3s;
        }

        // .light-glow-container {
        //     width: 75% !important;
        //     position: absolute;
        //     top: 6% !important;
        //     opacity: 0;
        //     filter: blur(25px);
        //     animation: lights-on 0.5s ease-in forwards 3s,
        //     bounce-glow 1.5s ease-in-out forwards 3.5s infinite;
        //     mix-blend-mode: hard-light;
        // }

        // .light-glow {
        //     top: 0;
        //     left: 0;
        //     fill: #efda18;
        //     opacity: 1;
        // }

        .logotype {
            width: 100% !important;
            fill: transparent;
            stroke: white;
            animation: logotype-fill 0.5s ease-in forwards 3s;
            margin-top: 20px;
            overflow: visible;
        }
        .logotype-container {
            position: relative;
            width: 100%;
        }
        .logotype-container::after {
            position: absolute;
            width: 100% !important;
        }
    }

    @media screen and (orientation: landscape) {
        .circle-container {
            width: 70% !important;
            padding-top: 70% !important;
        }
        .logo-container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            height: unset !important;
            width: unset !important;
        }
    }

    .logo-container {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .circle-container {
        width: 90%;
        height: 0;
        padding-top: 90%;
        text-align: center;
        position: relative;
        border-radius: 50%;
        overflow: hidden;
    }

    .logo-cropper {
        width: 100%;
        background-color: $my-black;
        position: absolute;
        top: 0;
        left: 0;
    }
    .head {
        transform: translate(5px, 39px);
        animation: head 3s ease forwards, animation,
            bounce-head 1.5s ease-in-out forwards 3.5s infinite;
    }
    .lightbulb {
        transform: translate(5px, 5px);
        animation: bounce 1.5s ease-in-out forwards 3.5s infinite;
    }

    .lightbulb-outline {
        stroke-dasharray: 56.4px;
        stroke-dashoffset: 56.4px;
        stroke: white;
        stroke-width: 0.5px;
        fill: transparent;
        animation: lightbulb 2.5s ease forwards, fill 0.5s ease forwards 2.5s;
    }

    .light {
        opacity: 0;
        animation: lights-on 0.5s ease-in forwards 3s;
    }

    // .light-glow-container {
    //     width: 100%;
    //     position: absolute;
    //     top: 0;
    //     left: 50%;
    //     transform: translate(-50%, 6%);
    //     opacity: 0;
    //     filter: blur(25px);
    //     animation: lights-on 0.5s ease-in forwards 3s,
    //         bounce-glow 1.5s ease-in-out forwards 3.5s infinite;
    //     mix-blend-mode: hard-light;
    // }

    // .light-glow {
    //     fill: #efda18;
    //     opacity: 1;
    // }

    // @keyframes bounce-glow {
    //     0% {
    //         transform: translate(-50%, 6%);
    //         filter: blur(25px);
    //     }
    //     50% {
    //         transform: translate(-50%, 0);
    //         filter: blur(10px);
    //     }
    //     100% {
    //         transform: translate(-50%, 6%);
    //         filter: blur(25px);
    //     }
    // }

    @keyframes lightbulb {
        0% {
            stroke-dashoffset: 56.4px;
        }
        70% {
            stroke-dashoffset: 56.4px;
        }
        100% {
            stroke-dashoffset: 0;
        }
    }

    @keyframes bounce {
        0% {
            transform: translate(5px, 5px);
        }
        50% {
            transform: translate(5px, 2px);
        }
        100% {
            transform: translate(5px, 5px);
        }
    }

    @keyframes head {
        0% {
            transform: translate(5px, 39px);
        }
        20% {
            transform: translate(5px, 39px);
        }
        100% {
            transform: translate(5px, 10px);
        }
    }

    @keyframes bounce-head {
        0% {
            transform: translate(5px, 10px);
        }
        50% {
            transform: translate(5px, 12px);
        }
        100% {
            transform: translate(5px, 10px);
        }
    }

    @keyframes fill {
        0% {
            fill: transparent;
        }
        100% {
            fill: white;
        }
    }

    @keyframes lights-on {
        0% {
            opacity: 0;
        }
        100% {
            opacity: 1;
        }
    }

    .logotype {
        fill: transparent;
        stroke: white;
        width: 100%;
        animation: logotype-fill 0.5s ease-in forwards 3s;
        position: relative;
        margin-top: 20px;
    }

    .logotype-container {
        position: relative;
    }

    .logotype-container::after {
        content: "";
        background-image: url("/logotype.svg");
        background-repeat: no-repeat;
        position: absolute;
        top: 20px;
        left: 50%;
        transform: translateX(-50%);
        height: 100%;
        width: 100%;
        opacity: 0;
        filter: blur(3px);
        animation: neon 0.5s ease-in forwards 3s, neon-bzz 6s forwards 3.5s infinite;
        z-index: -1;
    }

    #logotype path:nth-child(1) {
        stroke-dasharray: 11.98px;
        stroke-dashoffset: 11.98px;
        animation: letter-animation 1s ease-in-out forwards;
    }
    #logotype path:nth-child(2) {
        stroke-dasharray: 23.19px;
        stroke-dashoffset: 23.19px;
        animation: letter-animation 1s ease-in-out forwards 0.1s;
    }
    #logotype path:nth-child(3) {
        stroke-dasharray: 13.35px;
        stroke-dashoffset: 13.35px;
        animation: letter-animation 1s ease-in-out forwards 0.2s;
    }
    #logotype path:nth-child(4) {
        stroke-dasharray: 27.89px;
        stroke-dashoffset: 27.89px;
        animation: letter-animation 1s ease-in-out forwards 0.3s;
    }
    #logotype path:nth-child(5) {
        stroke-dasharray: 21.51px;
        stroke-dashoffset: 21.51px;
        animation: letter-animation 1s ease-in-out forwards 0.4s;
    }
    #logotype path:nth-child(6) {
        stroke-dasharray: 20.53px;
        stroke-dashoffset: 20.53px;
        animation: letter-animation 1s ease-in-out forwards 0.5s;
    }
    #logotype path:nth-child(7) {
        stroke-dasharray: 22.78px;
        stroke-dashoffset: 22.78px;
        animation: letter-animation 1s ease-in-out forwards 0.6s;
    }
    #logotype path:nth-child(8) {
        stroke-dasharray: 30.68px;
        stroke-dashoffset: 30.68px;
        animation: letter-animation 1s ease-in-out forwards 0.7s;
    }
    #logotype path:nth-child(9) {
        stroke-dasharray: 27.91px;
        stroke-dashoffset: 27.91px;
        animation: letter-animation 1s ease-in-out forwards 0.8s;
    }
    #logotype path:nth-child(10) {
        stroke-dasharray: 12px;
        stroke-dashoffset: 12px;
        animation: letter-animation 1s ease-in-out forwards 0.9s;
    }
    #logotype path:nth-child(11) {
        stroke-dasharray: 13.33px;
        stroke-dashoffset: 13.33px;
        animation: letter-animation 1s ease-in-out forwards 1s;
    }
    #logotype path:nth-child(12) {
        stroke-dasharray: 22.78px;
        stroke-dashoffset: 22.78px;
        animation: letter-animation 1s ease-in-out forwards 1.1s;
    }
    #logotype path:nth-child(13) {
        stroke-dasharray: 22.31px;
        stroke-dashoffset: 22.31px;
        animation: letter-animation 1s ease-in-out forwards 1.2s;
    }
    #logotype path:nth-child(14) {
        stroke-dasharray: 27.03px;
        stroke-dashoffset: 27.03px;
        animation: letter-animation 1s ease-in-out forwards 1.3s;
    }
    #logotype path:nth-child(15) {
        stroke-dasharray: 13.36px;
        stroke-dashoffset: 13.36px;
        animation: letter-animation 1s ease-in-out forwards 1.4s;
    }
    #logotype path:nth-child(16) {
        stroke-dasharray: 10.56px;
        stroke-dashoffset: 10.56px;
        animation: letter-animation 1s ease-in-out forwards 1.5s;
    }
    #logotype path:nth-child(17) {
        stroke-dasharray: 22.78px;
        stroke-dashoffset: 22.78px;
        animation: letter-animation 1s ease-in-out forwards 1.6s;
    }

    @keyframes letter-animation {
        to {
            stroke-dashoffset: 0px;
        }
    }

    @keyframes logotype-fill {
        to {
            fill: white;
        }
        }

        @keyframes neon {
        0% {
        }
        100% {
            opacity: 0.7;
        }
    }

    @keyframes neon-bzz {
        0% {
            opacity: 0.5;
        }
        20% {
            opacity: 0.7;
        }
        22% {
            opacity: 0.2;
            filter: blur(1px);
        }
        24% {
            opacity: 0.7;
            filter: blur(3px);
        }
        60% {
            opacity: 0.7;
        }
        61% {
            opacity: 0.2;
            filter: blur(1px);
        }
        62% {
            opacity: 0.7;
            filter: blur(3px);
        }
        70% {
            opacity: 0.7;
        }
        71% {
            opacity: 0.2;
            filter: blur(1px);
        }
        72% {
            opacity: 0.5;
            filter: blur(3px);
        }
    }

    @keyframes neon-bzz-typo {
        0% {
            opacity: 0.7;
        }
        20% {
            opacity: 1;
        }
        22% {
            opacity: 0.2;
            filter: blur(1px);
        }
        24% {
            opacity: 1;
            filter: blur(3px);
        }
        60% {
            opacity: 1;
        }
        61% {
            opacity: 0.2;
            filter: blur(1px);
        }
        62% {
            opacity: 1;
            filter: blur(3px);
        }
        70% {
            opacity: 1;
        }
        71% {
            opacity: 0.2;
            filter: blur(1px);
        }
        72% {
            opacity: 0.7;
            filter: blur(3px);
        }
    }
</style>
