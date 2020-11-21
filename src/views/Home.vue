<template>
  <div class="home">
    <portnavbar :navbar-content="navbarcontent"></portnavbar>
    <portbanner :banner-content="bannercontent"></portbanner>
    <portskills :data="skillscontents"></portskills>
    <portcontactform></portcontactform>
    <portfooter :footer-content="footercontent"></portfooter>
  </div>
</template>

<script>
// @ is an alias to /src
import portnavbar from "@/components/portnavbar.vue";
import portbanner from "@/components/portbanner.vue";
import portskills from "@/components/portskills.vue";
import portfooter from "@/components/portfooter.vue";
import portcontactform from "@/components/portcontactform.vue";


export default {
  name: "Home",
  components: {
    portnavbar,
    portbanner,
    portskills,
    portfooter,
    portcontactform
  },
  data: () => ({
    navbarcontent: [
      {
        text: "ABOUT ME",
        url: "/#about-me",
      },{
        text: "SKILLS",
        url: "/#portskills",
        id:"#portskillsbtn"
      },{
        text: "WORKS",
        url: "/#works",
      },{
        text: "CONTACT ME",
        url: "/#contact-me",
      }
    ],
    bannercontent: {
    
      img:"../img/port-img.png",
      title: "Frontend Developer",
      subtitle: "Let's bring your designs to life.",
      fontawesomeclass:'fas fa-code'
    },
    skillscontents: {
      img:"../img/port-img.png",
      title: "Hi! I'm Juani and I'm a Mid Level Web Developer.",
      subtitle: "I have 3 years experience as a Mid Web Developer specializing in front end development. <br>Developed Ecommerce, Informative Website and Travel Website. PSD to HTML/Website. <br>My hobbies are playing my guitar, outdoor activies and playing PC games.",
      langtoolstitle:"Languages and Tools",
      tabstitlecontents: [
        {
          tabtitle:'Frontend',
          tabtitleclass:'nav-link active',
          tabtitlelink:'#tabs-1'
        }, {
          tabtitle:'Backend',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-2'
        }, {
          tabtitle:'Deployment',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-3'
        }, {
          tabtitle:'Others',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-4'
        }
      ],
      tabscontent: [
        {
          tabcontentclass:'tab-pane active',
          tabcontentid:'tabs-1',
          contents: [
            {
              content:'PSD to Wordpress',
              fontawesomeclass:'fab fa-wordpress',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'PSD to Vue Js / Vue Bootstrap ',
              fontawesomeclass:'fab fa-vuejs',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'PSD to Angular 8 - 9 / Angular Material',
              fontawesomeclass:'fab fa-angular',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'jQuery / Javascript / Typescript',
              fontawesomeclass:'fab fa-js',
              progressbarid:'sixty-five',
              percentagecontent:'65%'
            },{
              content:'PSD to HTML5',
              fontawesomeclass:'fab fa-html5',
              progressbarid:'ninety',
              percentagecontent:'90%'
            },{
              content:'Bootstrap',
              fontawesomeclass:'fab fa-bootstrap',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'CSS3',
              fontawesomeclass:'fab fa-css3-alt',
              progressbarid:'ninety',
              percentagecontent:'90%'
            },{
              content:'SASS/SCSS',
              fontawesomeclass:'fab fa-sass',
              progressbarid:'seventy',
              percentagecontent:'70%'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'tabs-2',
          contents: [
            {
              content:'PHP',
              fontawesomeclass:'fab fa-php',
              progressbarid:'fifty',
              percentagecontent:'50%'
            }, {
              content:'MySQL / MariaDB',
              fontawesomeclass:'fas fa-database',
              progressbarid:'fifty',
              percentagecontent:'50%'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'tabs-3',
          contents: [
            {
              content:'SSH / FTP / SFTP',
              fontawesomeclass:'fas fa-terminal',
              progressbarid:'ninety',
              percentagecontent:'90%'
            },{
              content:'Git',
              fontawesomeclass:'fas fa-code-branch',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'Website / Domain Hosting / Email',
              fontawesomeclass:'fas fa-server',
              progressbarid:'eighty',
              percentagecontent:'80%'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'tabs-4',
          contents: [
            {
              content:'Office Work',
              fontawesomeclass:'fas fa-keyboard',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'Computer Software/Hardware Installation',
              fontawesomeclass:'fas fa-microchip',
              progressbarid:'ninety',
              percentagecontent:'90%'
            },{
              content:'Computer Troubleshooting',
              fontawesomeclass:'fas fa-exclamation-triangle',
              progressbarid:'ninety',
              percentagecontent:'90%'
            }
          ]
        }
      ]
    },
    footercontent: {
      text: "Design and Developed by Juanito Llera Parafina III",
    },
  })
};
</script>
