<template>
    <div id="projects" class="projects">
        <SectionTitle title="Projects" />
        <ProjectPreview 
            v-for="(project, index) in placeholder"
            :key="'project'+index" 
            :v-if="placeholder.length > 0 "
            :project="project"
            class="preview"
        />
    </div>
</template>

<script>
import SectionTitle from '../customs/SectionTitle'
import ProjectPreview from '../customs/ProjectPreview'

export default {
    name: "Projects",
    components:{
        SectionTitle,
        ProjectPreview
    },
    data:function () {
        return {
            placeholder:[
                {
                    title:"Infinity Bot List",
                    links:{link:"https://infinitybots.gg", github:"https://github.com/InfinityBotList"},
                    skills:["Typescript", "React", "Next.js", "Go-Lang", "Rust"],
                    image:["/img/projects/ibl_sample1.png", "/img/projects/ibl_sample2.png"],
                    description:"Infinity is the future of Discord Bot Listing Services, we make it easier for you to advertise and grow your bots using our Premium Features, Bot Packs, Short Links and Custom Widgets.",
                },
                {
                    title: "Link Cord",
                    links: { link: "https://linkcord.bio", github: "https://github.com/LinkCordApp"},
                    skills: ["Typescript", "React", "Next.js", "Firebase"],
                    image: ["/img/projects/linkcord_sample1.png", "/img/projects/linkcord_sample2.png"],
                    description: "Create your custom Profile Page add your Social Media Links and share it for the world to see."
                },
                {
                    title: "Job Cord",
                    links: { link: "https://beta.jobcord.co", github: "https://github.com/DscJobs"},
                    skills: ["Typescript", "React", "Next.js", "Go-Lang"],
                    image: ["/img/projects/jobcord_sample1.png", "/img/projects/jobcord_sample2.png"],
                    description: "Discord Server Moderators and Developers at your fingertips, browse our vast list of users today!"
                },
                {
                    title: "DisWidgets",
                    links: { link: "https://beta.diswidgets.org", github: "https://github.com/DisWidgets"},
                    skills: ["Typescript", "React", "Next.js", "Mongoose"],
                    image: ["/img/projects/diswidgets_sample1.png", "/img/projects/diswidgets_sample2.png"],
                    description: "A Free, Stylish and Simple solution for sharing your Discord Server across the web!"
                },
            ]
        }
    },
    
}
</script>

<style scoped lang="scss">
@import '@/assets/_shared.scss';
.projects{
    // min-height: 100vh;
    padding: 80px 0;
    .preview{
        &:last-child {
            border-bottom: none !important;
            padding-bottom: 0;
        }
        &:nth-child(2) {
            padding-top: 0 !important;
        }
    }
}

</style>
