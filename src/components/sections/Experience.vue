<template>
    <div id="experience" class="experience">
        <SectionTitle title="Experience" />

        <ExperiencesAccordion 
            v-for="(experience, index) in placeholder"
            :id="index" 
            :key="'experience'+index"
            :v-if="placeholder.length > 0 "
            :experience="experience"
        />
        
    </div>
</template>

<script>
import SectionTitle from '../customs/SectionTitle'
import ExperiencesAccordion from '../customs/ExperiencesAccordion'

export default {
    name: "Experience",
    components:{
        SectionTitle,
        ExperiencesAccordion
    },
    data:function () {
        return {
            placeholder:[
                {
                    title:"Full-Stack Development",
                    institution: "FreeCodeCamp.org",
                    date: "Jan 2020 - Jul 2020",
                    image:"/img/experience/fcc.png",
                    description:"Upon completion of all six certificates, the freeCodeCamp Full Stack Development Program Certificate will be issued. This final distinction signifies completion of approximately 1,800 hours of coding with exposure to a wide range of web development tools."
                },
                {
                    title:"Responsive Web Design",
                    institution: "FreeCodeCamp.org",
                    date: "Jul 2019 - Nov 2019",
                    image:"/img/experience/fcc.png",
                    description:"In this Responsive Web Design Certification, i learnt the languages that developers use to build webpages: HTML (Hypertext Markup Language) for content, and CSS (Cascading Style Sheets) for design."
                },
                {
                    title:"React Development",
                    institution: "FreeCodeCamp.org",
                    date: "Jan 2018 - May 2018",
                    image:"/img/experience/fcc.png",
                    description:"ReactJS (aka React) is an open-source JavaScript-based user interface library. It is insanely popular in web development communities today. "
                },
                {
                    title:"Typescript Development",
                    institution: "FreeCodeCamp.org",
                    date: "Jan 2017 - Jan 2018",
                    image:"/img/experience/fcc.png",
                    description:"TypeScript is a language created by Microsoft which adds some nice features which JavaScript is missing, the most obvious of which is static typing as is found in many other languages."
                },
                
            ]
        }
    },
    
}
</script>

<style scoped lang="scss">

    @import '@/assets/_shared.scss';

    .experience{
        // min-height: 100vh;
        padding: 80px 0;
        .button-container {
            margin-top: 20px;
            text-align: center;
        }
    }

</style>
