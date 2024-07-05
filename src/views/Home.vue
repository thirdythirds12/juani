<template>
  <div class="home">
    <portnavbar :navbar-content="navbarcontent"></portnavbar>
    <portbanner :banner-content="bannercontent"></portbanner>
    <portskills :data="skillscontents"></portskills>
    <portprojects :data="projcontents"></portprojects>
    <!-- <portcontactform></portcontactform> -->
    <portcta :data="ctacontents"></portcta>
    <portfooter :footer-content="footercontent"></portfooter>
  </div>
</template>

<script>
// @ is an alias to /src
import portnavbar from "@/components/portnavbar.vue";
import portbanner from "@/components/portbanner.vue";
import portskills from "@/components/portskills.vue";
import portprojects from "@/components/portprojects.vue";
import portcta from "@/components/portcta.vue";
import portfooter from "@/components/portfooter.vue";
// import portcontactform from "@/components/portcontactform.vue";


export default {
  name: "Home",
  components: {
    portnavbar,
    portbanner,
    portskills,
    portprojects,
    portcta,
    portfooter,
    // portcontactform
  },
  data: () => ({
    navbarcontent: [
      {
        text: "ABOUT ME",
        url: "/#about-me"
      },{
        text: "SKILLS",
        url: "/#skills"
      },{
        text: "PROJECTS",
        url: "/#projects",
      },{
        text: "CONTACT ME",
        url: "/#contact-me",
      }
    ],
    bannercontent: {
    
      img:"../img/port-img.png",
      title: "Web Developer",
      // subtitle: "Let's bring your designs to life.",
      fontawesomeclass:'fas fa-code'
    },
    skillscontents: {
      title: "Hi! I'm Juani and I'm a Web Developer.",
      subtitle: "I have 5 years and 6 months experience as a Web Developer specializing in front end development. <br>Developed Ecommerce, Informative Website and Travel Website. PSD to HTML/Website. <br>I also have experience of creating an informative website generating reusable components using Vue Js and Angular 8 - 9.",
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
          tabtitle:'Deployment / Tools',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-3'
        }, {
          tabtitle:'Software / Hardware',
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
              fontawesomeclass:'fab fa-wordpress wp-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
              
            },{
              content:'PSD to Vue Js / Vue Bootstrap Panel Components',
              fontawesomeclass:'fab fa-vuejs vue-c',
              progressbarid:'fifty',
              percentagecontent:'50%'
            },{
              content:'PSD to Angular 8 - 9 / Angular Material Panel Components',
              fontawesomeclass:'fab fa-angular ng-c',
              progressbarid:'fifty',
              percentagecontent:'50%'
            },{
              content:'jQuery / Javascript / Typescript',
              fontawesomeclass:'fab fa-js js-c',
              progressbarid:'fifty',
              percentagecontent:'50%'
            },{
              content:'PSD to HTML5',
              fontawesomeclass:'fab fa-html5 html-c',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'Bootstrap',
              fontawesomeclass:'fab fa-bootstrap boots-c',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'CSS3',
              fontawesomeclass:'fab fa-css3-alt css-c',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'SASS/SCSS',
              fontawesomeclass:'fab fa-sass sass-c',
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
              fontawesomeclass:'fab fa-php php-c',
              progressbarid:'fifty',
              percentagecontent:'50%'
            }, {
              content:'MySQL / MariaDB',
              fontawesomeclass:'fas fa-database default-c',
              progressbarid:'fifty',
              percentagecontent:'50%'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'tabs-3',
          contents: [
            {
              content:'NPM',
              fontawesomeclass:'fab fa-npm npm-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'SSH / FTP / SFTP',
              fontawesomeclass:'fas fa-terminal default-c',
              progressbarid:'ninety',
              percentagecontent:'90%'
            },{
              content:'Git',
              fontawesomeclass:'fas fa-code-branch git-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'Website / Domain Hosting / Email',
              fontawesomeclass:'fas fa-server server-c',
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
              fontawesomeclass:'fas fa-keyboard office-c',
              progressbarid:'eighty',
              percentagecontent:'80%'
            },{
              content:'Computer Software/Hardware Installation/Troubleshooting',
              fontawesomeclass:'fas fa-microchip default-c',
              progressbarid:'ninety',
              percentagecontent:'90%'
            },{
              content:'Computer Troubleshooting',
              fontawesomeclass:'fas fa-exclamation-triangle trouble-c',
              progressbarid:'ninety',
              percentagecontent:'90%'
            }
          ]
        }
      ]
    },
    projcontents: {
      title: "Projects",
      subtitle: "Here are some of the projects I have participated.",
      tabstitlecontents: [
        {
          tabtitle:'Wordpress',
          tabtitleclass:'nav-link active',
          tabtitlelink:'#projtabs-1'
        }, {
          tabtitle:'Angular 8-9',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#projtabs-2'
        }, {
          tabtitle:'Vue.js',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#projtabs-3'
        }
      ],
      tabscontent: [
        {
          tabcontentclass:'tab-pane active',
          tabcontentid:'projtabs-1',
          contents: [
            {
              projectimg:'../img/grey.jpg',
              projecttitle:'Grey Legal',
              projecttype:'Corporate Lawyer Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://www.greylegal.com.au/'
            },{
              projectimg:'../img/alpha.jpg',
              projecttitle:'Alpha Car Hire',
              projecttype:'Corporate Website',
              projectyear:'2022',
              projectposition:'Lead Frontend Developer',
              projectlink:'https://alphacarhire.com.au/'
            },{
              projectimg:'../img/ca.jpg',
              projecttitle:'College Australia',
              projecttype:'School Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://collegeaustralia.edu.au/'
            },{
              projectimg:'../img/kode.jpg',
              projecttitle:'Kode <br>Access',
              projecttype:'E-Commerce Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://kodeaccess.com.au/'
            },{
              projectimg:'../img/sengs.jpg',
              projecttitle:'SENGS <br>Sales & Service',
              projecttype:'Informative E-Commerce Level Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://sengs.com.au/'
            },{
              projectimg:'../img/dbos.jpg',
              projecttitle:'Dynamic Business Outsourcing Solutions',
              projecttype:'Corporate Website',
              projectyear:'2021',
              projectposition:'Lead Developer',
              projectlink:'https://dbos.com.au/'
            },{
              projectimg:'../img/mnski.jpg',
              projecttitle:'Mineski Global',
              projecttype:'Corporate Website',
              projectyear:'2020',
              projectposition:'Lead Developer',
              projectlink:'https://www.mineskiglobal.com/'
            },{
              projectimg:'../img/crbn.jpg',
              projecttitle:'CarbonTrack UK',
              projecttype:'Corporate Website',
              projectyear:'2020',
              projectposition:'Lead Developer',
              projectlink:'https://carbontrackuk.co.uk/'
            },{
              projectimg:'../img/dqtsi.jpg',
              projecttitle:'DynaQuest',
              projecttype:'Corporate Website',
              projectyear:'2020',
              projectposition:'Lead Developer',
              projectlink:'https://dqtsi.com/'
            },{
              projectimg:'../img/sit.jpg',
              projecttitle:'Situp PH',
              projecttype:'Informative Website',
              projectyear:'2019',
              projectposition:'Lead Developer',
              projectlink:'https://dqtsi.com/'
            },{
              projectimg:'../img/sha.jpg',
              projecttitle:'ShawarmaHouse PH',
              projecttype:'Informative Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://www.shawarmahouseph.com/'
            },{
              projectimg:'../img/tgs.jpg',
              projecttitle:'The Greencross Saga',
              projecttype:'Informative Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://www.thegreencrosssaga.com/'
            },{
              projectimg:'../img/comark.jpg',
              projecttitle:'Comark PH',
              projecttype:'E-Commerce Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://comark.com.ph/'
            },{
              projectimg:'../img/tyd.jpg',
              projecttitle:'TYD Automotive AU',
              projecttype:'E-Commerce Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://tydautomotive.com.au/'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'projtabs-2',
          contents: [
            {
              projectimg:'../img/gep.jpg',
              projecttitle:'Gepstudies AU',
              projecttype:'Corporate Website',
              projectyear:'2019',
              projectposition:'Frontend Developer',
              projectlink:'https://www.gepstudies.com/'
            },{
              projectimg:'../img/maj.jpg',
              projecttitle:'Majestic Ventures Group',
              projecttype:'Corporate Website',
              projectyear:'2018',
              projectposition:'Frontend Developer',
              projectlink:'https://www.majesticventures.group/'
            },{
              projectimg:'../img/noac.jpg',
              projecttitle:'NOAC Consultant AU',
              projecttype:'Corporate Website',
              projectyear:'2018',
              projectposition:'Frontend Developer',
              projectlink:'https://www.noac.net.au/'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'projtabs-3',
          contents: [
            {
              projectimg:'../img/gwf.jpg',
              projecttitle:'Global WebForce',
              projecttype:'Corporate Website',
              projectyear:'2017',
              projectposition:'Frontend Developer',
              projectlink:'https://www.globalwebforce.com/'
            }
          ]
        }
      ]
    },
    ctacontents: {
      title:'Contact & Social Media Details',
      contents: [
         {
          fontawesomeclass:'fas fa-mobile',
          contactlink:'tel:+63 905 426 9814',
          contactcontent:'+63 905 426 9814'
         },{
          fontawesomeclass:'fas fa-mail-bulk',
          contactlink:'mailto:juaniparafina@gmail.com',
          contactcontent:'juaniparafina@gmail.com'
         },{
          fontawesomeclass:'fab fa-linkedin',
          contactlink:'https://www.linkedin.com/in/juanito-llera-parafina-iii-4985301a5',
          contactcontent:'LinkedIn Profile'
         },{
          fontawesomeclass:'fab fa-facebook-square',
          contactlink:'https://www.facebook.com/thirdz.parafina',
          contactcontent:'Facebook Profile'
         }
      ]
    },
    footercontent: {
      text: "Design and Developed by Juanito Llera Parafina III",
    },
  })
};
</script>
