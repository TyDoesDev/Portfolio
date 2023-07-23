<template>
    <div id="about" class="about">
        <SectionTitle title="About" />
        <div class="about-content">
            <div class="bio">
                <p class="bio-text">
                    I am a curious by nature self-taught full-stack software developer who is always aiming for improvement 
                    with a strong background in project management, project planning and customer relations.
                    <br /><br />
                    I also specialize in discord bot development, web development, frontend development and am well Experienced 
                    with all stages of the development cycle for dynamic web projects.
                </p>
                <div class="skillset">
                    <p class="skillset-introduction">
                        My skillset includes:<br><br>
                    </p>
                    <div class="skillset-tables">
                        <table>
                            <thead>
                                <tr>
                                    <th>Development</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>HTML</td>
                                    <td>React</td>
                                    <td>Node.js</td>
                                </tr>
                                <tr>
                                    <td>(S)CSS</td>
                                    <td>Vue.js</td>
                                    <td>Next.js</td>
                                </tr>
                                <tr>
                                    <td>Go Lang</td>
                                    <td>JavaScript</td>
                                    <td>Typescript</td>
                                </tr>
                            </tbody>
                        </table>
                        <table>
                            <thead>
                                <tr>
                                    <th>Design</th>
                                </tr>    
                            </thead>
                            <tbody>
                                <tr>
                                    <td>Photoshop</td>
                                    <td>Premier</td>
                                    <td>InDesign</td>
                                </tr>
                                <tr>
                                    <td>Illustrator</td>
                                    <td>Figma</td>
                                    <td>Canvas</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
                
            </div>
            <div class="portrait">
                <div class="portrait-inner">
                    <img src="img/about/TyDoesDev.jpg" alt="uWu" class="portrait-image">
                </div>
            </div>
            
        </div>
    </div>
</template>

<script>

import SectionTitle from '../customs/SectionTitle'

export default {
    name: "About",
    components: {
        SectionTitle,
    }
}
</script>

<style scoped lang="scss">
    @import "@/assets/_shared.scss";

    .about {
        //min-height: 100vh;
        padding: 80px 0;
        #{&}-content{
            display: flex;
            flex-direction: column;
            .bio {
                display: inline-block;
                order: 2;
                &-text {
                    margin-bottom: 20px;
                }
                .skillset{
                    display: table;
                    margin: 0 auto;
                    &-introduction{
                        display: inline-block;
                    }
                    &-tables {
                        display: flex;
                        flex-direction: column;
                        table{
                            max-width: 300px;
                            tr{
                                
                                &:nth-child(1){
                                    td{
                                        padding-top: 10px;
                                    }
                                }
                                th {
                                    display:table-header-group;
                                }
                                
                                td{
                                    font-size: 16px;
                                    min-width: 100px;
                                    max-width: 120px;
                                    padding-bottom: 5px;
                                    &::before{
                                        content:"▹ "
                                    }
                                }
                            }
                            
                            &:nth-child(1){
                                padding: 0 0 10px 0;
                                border-bottom: $my-white 1px solid;
                            }
                            &:nth-child(2){
                                padding:10px 0 0 0;
                            }
                        }
                        
                    }
                }
                
            }
            .portrait {
                width: 80%;
                padding-top: 80%;
                order: 1;
                border-radius: 50%;
                overflow: hidden;
                position: relative;
                margin: 0 auto 20px auto;
                min-width: 230px;
                min-height: 230px;
                &-image {
                    top:0;
                    position: absolute;
                    object-fit: cover;
                    object-position: center;
                    width: 100%;
                    height: 100%;
                    @include transition-experience(filter);
                    filter: grayscale(100);
                    &:hover {
                        filter: grayscale(0);
                    }
                }
            }
        }
    }


    @media screen and (min-width: $SM) {
        .about {
            padding: 80px 0;
            #{&}-content{
                display: flex;
                flex-direction: column;
                .bio {
                    display: inline-block;
                    order: 2;
                }
                .portrait {
                    width: 50%;
                    padding-top: 50%;
                    order: 1;
                    border-radius: 50%;
                    overflow: hidden;
                    position: relative;
                    margin: 0 auto 20px auto;
                    &-image {
                        top:0;
                        position: absolute;
                        object-fit: cover;
                        object-position: center;
                        width: 100%;
                        height: 100%;

                    }
                }
            }
        }
    }

    @media screen and (min-width: $MD) {
        .about {
            padding: 80px 0;
            #{&}-content{
                display: flex;
                flex-direction: row;
                .bio {
                    display: inline-block;
                    flex: 2;
                    order: 1;
                    padding-right: 20px;
                    .skillset{
                        margin: 0 ;
                    }
                }
                .portrait {
                    flex: 1;
                    order: 2;
                    margin: 10% 0 auto 0;
                    padding-top: 0;
                     &-inner{
                         padding-top: 100%;
                    }
                }
            }
        }
    }
    @media screen and (min-width: $LG) {
        .about {
            #{&}-content{
                .bio{
                    .skillset-tables {
                        flex-direction: row !important;
                        table{
                            max-width:initial !important;
                            th {
                                display:table-header-group;
                            }
                            td{
                                font-size: 14px !important;
                                min-width: 100px !important;
                                max-width: 140px !important;
                                &::before{
                                    content:"▹ "
                                }
                            }
                            &:nth-child(1){
                                padding: 0 10px 0 0 !important;
                                border-bottom: none !important;
                                border-right: $my-white 1px solid;
                            }
                            &:nth-child(2){
                                padding: 0 0 0 10px !important;
                            }
                        }
                    }
                }
                .portrait {
                    margin: auto 0;
                    padding-top: 0;
                }
            }
        }
    }

    
</style>
