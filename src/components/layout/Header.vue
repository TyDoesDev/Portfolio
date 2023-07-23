<template>
    <div id="header" class="header">
        <div id="hamburger-menu-container" class="hamburger-menu-container hamburger" @click="open">
            <svg class="hamburger-icon" viewBox="0 0 45 20">
                <rect y="0"/>
                <rect y="9"/>
                <rect y="18"/>
            </svg>
            <div id="navbar-small" class="navbar-small divider-out">
                <ul class="nav-links">
                    <a href="#about" class="nav-link">
                        <li class="nav-item">
                            About
                        </li>
                    </a>
                    <a href="#experience" class="nav-link">
                        <li class="nav-item">
                            Experience
                        </li>
                    </a>
                    <a href="#projects" class="nav-link">
                        <li class="nav-item">
                            Projects
                        </li>
                    </a>
                    <a href="#contacts" class="nav-link">
                        <li class="nav-item">
                            Contact Me
                        </li>
                    </a>
                </ul>
            </div>
        </div>
        <div class="nav-logo-container">
            <a href="#hero" class="nav-logo-link"> 
                <v-img src="/img/about/TyDoesDev.jpg" alt="uWu ❤️"
                       height="150px"
                       width="150px">
                </v-img>
            </a>
        </div>
        <div class="navbar">
            <ul class="nav-links">
                <a href="#about" class="nav-link">
                    <li class="nav-item">
                        About
                    </li>
                </a>
                <a href="#experience" class="nav-link">
                    <li class="nav-item">
                        Experience
                    </li>
                </a>
                <a href="#projects" class="nav-link">
                    <li class="nav-item">
                        Projects
                    </li>
                </a>
                <a href="#contacts" class="nav-link">
                    <li class="nav-item">
                        Contacts
                    </li>
                </a>
            </ul>
            <div>
                <a href="https://github.com/TyDoesDev"> <Button class="nav-button" child="GitHub"/> </a>
            </div>
        </div>
    </div>
    
</template>

<script>
import Button from '../customs/Button'
export default {
    name:"Header",
    components: {
        Button
    },
    methods:{
        open(){
            const navbar = document.getElementById("navbar-small")
            const menuLogo = document.getElementById('hamburger-menu-container')
            navbar.classList.toggle("navbar-small-open")
            navbar.classList.toggle("divider-out")
            menuLogo.classList.toggle("hamburger-menu-container-open")
            menuLogo.classList.toggle("hamburger-menu-container")
        }
    }
}
</script>

<style scoped lang="scss">

@import '@/assets/_shared.scss';

.header {
    padding: 0 25px;
    transition: padding 0.2s ease-in-out;
    height: 100px;
    display: flex;
    justify-content: space-between;
    background-color: $my-theme;
    box-shadow: 0px 7px 7px rgba($color: #000000, $alpha: 0.7);
    @include transition-header(padding margin top, 0s 0s 0s);
    // transition: padding 0.2s ease-in-out, margin 0.2s ease-in-out, top 0.2s ease-in-out;
    position: sticky;
    top: 0;
    left: 0;
    z-index: 1000;
    .hamburger{
        margin: auto 0;
        width: 45px;
        height: 20px;
        position: relative;
        &-icon {
            fill: $my-acqua;
            position: relative;
            rect {
                height: 2px;
                @include transition-header(height width, 0.2s 0.4s);
                // transition: height 0.2s ease-in-out 0.2s, width 0.2s ease-in-out 0.4s ;
            }
            rect:nth-child(1){
                width: 35px;
            }
            rect:nth-child(2){
                width: 40px;
            }
            rect:nth-child(3){
                width: 45px;
            }
        }
        .navbar-small {
            position:fixed;
            top: 100px;
            left: 0;
            width: 100%;
            height: 0;
            background-color: $my-black;
            @include transition-header(height, 0.2s);
            // transition: height 0.2s ease-in-out 0.2s,;
            overflow: hidden;
            box-shadow: 0px 7px 7px rgba($color: #000000, $alpha: 0.7);
            .nav-links {
                list-style: none;
                padding: 25px;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                flex-wrap: wrap;
                height: 100%;
                transition: padding 0.3s ease-in-out;
                .nav-link{
                    display: inline-flex;
                    .nav-item{
                        display:flex;
                        position: relative;
                        margin: 0 auto 0 0;
                        font-family: 'Inconsolata', monospace;
                        &::after{
                            content: "";
                            display:flex;
                            position: absolute;
                            left: 0;
                            bottom: -2px;
                            height: 0.5px;
                            background-color: $my-acqua;
                            width: 0;
                            @include transition-header(width, 0s);
                            // transition: width  0.2s ease-in-out;
                        }
                        &:hover::after {
                            width: 100%;
                        }
                    }
                }  
            }
        }
        .navbar-small-open {
            height: 150px;
            &::before{
                content:"";
                position: absolute;
                left: 0;
                width: 0;
                height: 1px;
                display: inline-block;
                background-color: $my-acqua;
                animation: navbar-divider 0.2s ease-in-out forwards 0.2s;
            }
        }
        .divider-out::before{
            content:"";
            position: absolute;
            left: 0;
            width: 100%;
            height: 1px;
            display: inline-block;
            background-color: $my-acqua;
            animation: navbar-divider-out 0.2s ease-in-out forwards;
        }
    }
    .hamburger-menu-container {
        &::after{
            content:"Menu";
            position: absolute;
            top: 2px;
            left:4px;
            height: 16px;
            width: 0;
            font-weight: 600;
            color: $my-acqua;
            box-sizing: border-box;
            overflow: hidden;
            font-family: 'Inconsolata', monospace;
            @include transition-header(width padding, 0s 0s);
            // transition: width 0.2s ease-in-out, padding 0.2s ease-in-out;
        }
        &:hover {
            height: 100%;
            .hamburger-icon {
                margin: 40px 0;
            }
            rect {
                width: 4px !important;
                height: 10px !important;
                @include transition-header(height width, 0.4s 0.2s);
                // transition: height 0.2s ease-in-out 0.4s, width 0.2s ease-in-out 0.2s ;
            }
            &::after{
                content:"Menu";
                position: absolute;
                top: 42px;
                left:4px;
                padding: 0 10px;
                height: 16px;
                width: 55px;
                font-family: 'Inconsolata', monospace;
                @include transition-header(width padding, 0.6s 0.6s);
                // transition: width 0.2s ease-in-out 0.6s, padding 0.2s ease-in-out 0.6s;
            }
        }
        &-open{
            margin: auto 0;
            width: 45px;
            position: relative;
            height: 100%;
            .hamburger-icon {
                margin: 40px 0;
            }
            rect {
                width: 4px !important;
                height: 10px !important;
                @include transition-header(height width, 0.4s 0.2s);
                // transition: height 0.2s ease-in-out 0.4s, width 0.2s ease-in-out 0.2s ;
            }
            &::after{
                content:"Close Menu";
                font-family: 'Inconsolata', monospace;
                position: absolute;
                top: 42px;
                left:4px;
                right:0;
                padding: 0 10px;
                height: 16px;
                width: 125px;
                color: $my-acqua;
                overflow: hidden;
                animation: close-menu 0.4s ease-in-out forwards;
            }
        }
    }
    .nav-logo-container {
        position: absolute;
        left: 50%;
        top: 50%;
        transform:translate(-50%, -50%);
        margin: auto 0;
        #nav-logo {
            height: 70px;
            width: 70px;
            .no-fill {
            fill: transparent;
            }
            .fill {
                fill: $my-white;
            }
            .light {
                fill: #efda18;
                display: none;
            }
            .steel {
                fill: #b5b5b4;
                display: none;
            }
        }
    }
    .navbar {
        margin: auto 0;
        display: flex;
        .nav-links {
            display: flex;
            list-style: none;
            flex-wrap: wrap;
            align-content: center;
            display: none;
        }
        .nav-item{
            display:flex;
            padding: 10px;
            margin: 0 5px;
            color: $my-white;
            position: relative;
            font-family: 'Inconsolata', monospace;
            &::after{
                content: "";
                display:flex;
                position: absolute;
                left: 0;
                bottom: 5px;
                height: 0.5px;
                background-color: $my-acqua;
                width: 0;
                @include transition-header(width, 0s);
                // transition: width  0.2s ease-in-out;
            }
            &:hover::after {
                width: 100%;
            }
        }
    }
    .nav-button {
        margin: 0;
        span {
            display: none;
        }
        i {
            display: block;
        }
    }
}

@media screen and (min-width: $SM ) {
    .header {
        padding: 0 50px;
        .navbar-small{
            .nav-links{
                padding: 25px 50px !important;
            }
        }
    }
  }

  @media screen and (min-width: $MD ) {
    .header {
        padding: 0 100px;
        .nav-logo-container {
            position: unset;
            left: 0%;
            top: 0%;
            transform:translate(0, 0);
        }
        .nav-links{
            display: flex !important;
        }
        .hamburger-menu-container{
            display: none;
        }
        .hamburger-menu-container-open {
            display: none;
        }
        .nav-button {
            margin: 0 0 0 15px;
            span {
                display: block;
            }
            i{
                display: none;
            }
        }
    }
  }

  @media screen and (min-width: $LG ) {
    .header {
        padding: 0 150px;
    }
  }

  @keyframes navbar-divider {
    0% {
        width: 0;
    }
    100% {
        width: 100%;
    }
  }

  @keyframes navbar-divider-out {
    0% {
        width: 100%;
    }
    100% {
        width: 0;
    }
  }

  @keyframes close-menu {
    0% {
        padding: 0;
        width: 0px;
    }

    100%{
        padding: 0 10px;
        width: 125px !important;
    }
  }

</style>
