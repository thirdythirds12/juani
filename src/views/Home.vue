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
      img:"/img/port-img.png",
      title: "Web Developer",
      name: "Juanito L. Parafina III",
      subtitle: "I build responsive websites, SaaS landing pages, and reusable front-end components for brands that need fast, modern digital experiences. With <strong>9+ years</strong> of experience.",
      fontawesomeclass:'fas fa-laptop-code'
    },
    skillscontents: {
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
          tabtitle:'Project Management',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-3'
        }, {
          tabtitle:'Deployment / Tools',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-4'
        }, {
          tabtitle:'Software / Hardware',
          tabtitleclass:'nav-link ',
          tabtitlelink:'#tabs-5'
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
              progressbarid:'eighty',
              percentagecontent:'80%'
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
              content:'ClickUp',
              imgsrc:'https://cdn.simpleicons.org/clickup/7B68EE',
              fontawesomeclass:'fas fa-clipboard-check default-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'Asana',
              imgsrc:'https://cdn.simpleicons.org/asana/FF6B6B',
              fontawesomeclass:'fab fa-asana default-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'Trello',
              imgsrc:'https://cdn.simpleicons.org/trello/0055CC',
              fontawesomeclass:'fab fa-trello trello-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
            },{
              content:'BaseCamp',
              imgsrc:'https://cdn.simpleicons.org/basecamp/8B7A5E',
              fontawesomeclass:'fab fa-basecamp default-c',
              progressbarid:'seventy',
              percentagecontent:'70%'
            }
          ]
        },{
          tabcontentclass:'tab-pane ',
          tabcontentid:'tabs-4',
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
          tabcontentid:'tabs-5',
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
      title: "A few places I’ve helped build and lead.",
      subtitle: "Great design starts with clarity, collaboration, and strong digital leadership.",
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
              projectimg:'../img/smartperformance.jpg',
              projecttitle:'Smart Performance',
              projecttype:'Health & Performance Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://smartperformance.ca/',
              projectsummary:'Health and performance business website focused on wellness, service credibility, and customer conversion.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/krakensec.jpg',
              projecttitle:'Kraken Security',
              projecttype:'Security Services Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://www.krakensec.ca/',
              projectsummary:'Security services business website designed to build trust, highlight expertise, and generate leads.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/innovativelightsiowa.jpg',
              projecttitle:'Innovative Lights Iowa',
              projecttype:'Outdoor Lighting Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://innovativelightsiowa.com/',
              projectsummary:'Outdoor lighting company website focused on product presentation, local service positioning, and lead generation.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/titanlogix.jpg',
              projecttitle:'Titan Logix',
              projecttype:'Industrial Measurement Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://titanlogix.com/',
              projectsummary:'Industrial technology business website built to explain complex products and reinforce technical credibility.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/raincoastelectric.jpg',
              projecttitle:'Raincoast Electric',
              projecttype:'Electrical Services Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://raincoastelectric.ca/',
              projectsummary:'Electrical services company website focused on local trust, service clarity, and customer enquiries.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/expresselectricinc.jpg',
              projecttitle:'Express Electric Inc',
              projecttype:'Electrical Services Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://expresselectricinc.ca/',
              projectsummary:'Electrical contracting business website designed around service pages, credibility, and stronger lead capture.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/xcessive.jpg',
              projecttitle:'Xcessive',
              projecttype:'Vehicle Graphics Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://xcessive.ca/',
              projectsummary:'Vehicle graphics and branding business website designed to showcase work and attract commercial leads.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/astorialighting.jpg',
              projecttitle:'Astoria Lighting',
              projecttype:'Permanent Lighting Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://astorialighting.ca/',
              projectsummary:'Permanent lighting business website focused on premium branding, product storytelling, and conversion.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/halocustomlighting.jpg',
              projecttitle:'Halo Custom Lighting',
              projecttype:'Outdoor Lighting Website',
              projectyear:'2026',
              projectposition:'Lead Developer / Project Manager',
              projectlink:'https://halocustomlighting.com/',
              projectsummary:'Custom lighting company website focused on premium positioning, service clarity, and customer enquiry flow.',
              projecthosting:'Pressable',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://bricksbuilder.io/wp-content/uploads/2023/07/bricks-logo.svg']
            },
            {
              projectimg:'../img/vit.jpg',
              projecttitle:'Vitalis Health',
              projecttype:'Healthcare Services Website',
              projectyear:'2025',
              projectposition:'Lead Developer',
              projectlink:'https://vitalis.health/',
              projectsummary:'Healthcare provider website focused on patient trust, service clarity, and appointment-led conversion.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/us.jpg',
              projecttitle:'Better Days US',
              projecttype:'Healthcare Services Website',
              projectyear:'2025',
              projectposition:'Lead / In-house Developer',
              projectlink:'https://betterdays.us/',
              projectsummary:'Healthcare services website focused on patient support, care messaging, and easy enquiry conversion.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/uk.jpg',
              projecttitle:'Better Days UK',
              projecttype:'Healthcare Services Website',
              projectyear:'2023 - 25',
              projectposition:'Lead / In-house Developer',
              projectlink:'https://betterdays.uk/',
              projectsummary:'Healthcare brand website designed around accessibility, service clarity, and patient-focused communication.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/nz.jpg',
              projecttitle:'Better Days NZ',
              projecttype:'Healthcare Services Website',
              projectyear:'2023 - 25',
              projectposition:'Lead / In-house Developer',
              projectlink:'https://betterdays.nz/',
              projectsummary:'Healthcare services website built for trust, service visibility, and a clearer patient journey.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/br.jpg',
              projecttitle:'Better Rehab AU',
              projecttype:'Healthcare Services Website',
              projectyear:'2023 - 25',
              projectposition:'Lead / In-house Developer',
              projectlink:'https://betterrehab.com.au/',
              projectsummary:'Rehabilitation services website focused on care messaging, trust, and conversion for new enquiries.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/six.jpg',
              projecttitle:'Sixgun',
              projecttype:'Digital Marketing Website',
              projectyear:'2023',
              projectposition:'Lead Developer',
              projectlink:'https://sixgun.com.au/',
              projectsummary:'Digital marketing business website focused on brand visibility, service positioning, and lead generation.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/grey.jpg',
              projecttitle:'Grey Legal',
              projecttype:'Corporate Lawyer Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://www.greylegal.com.au/',
              projectsummary:'Law firm website focused on professionalism, trust, and clear service information for prospective clients.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/alpha.jpg',
              projecttitle:'Alpha Car Hire',
              projecttype:'Corporate Website',
              projectyear:'2022',
              projectposition:'Lead Frontend Developer',
              projectlink:'https://alphacarhire.com.au/',
              projectsummary:'Car hire company website structured around booking ease, service transparency, and customer conversion.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','https://surniaulula.com/wp-content/uploads/2018/09/wp-bakery-logo-1200x1200-cropped.jpg']
            },
            {
              projectimg:'../img/ca.jpg',
              projecttitle:'College Australia',
              projecttype:'School Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://collegeaustralia.edu.au/',
              projectsummary:'Education and training website focused on course clarity, student engagement, and institutional credibility.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/kode.jpg',
              projecttitle:'Kode <br>Access',
              projecttype:'E-Commerce Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://kodeaccess.com.au/',
              projectsummary:'Access solutions and hardware business website focused on product browsing, trust, and enquiry conversion.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/sengs.jpg',
              projecttitle:'SENGS <br>Sales & Service',
              projecttype:'Informative E-Commerce Level Website',
              projectyear:'2022',
              projectposition:'Lead Developer',
              projectlink:'https://sengs.com.au/',
              projectsummary:'Service and product business website focused on navigation, trust, and smoother customer discovery.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/dbos.jpg',
              projecttitle:'Dynamic Business Outsourcing Solutions',
              projecttype:'Corporate Website',
              projectyear:'2021',
              projectposition:'Lead Developer',
              projectlink:'https://dbos.com.au/',
              projectsummary:'Business outsourcing and consulting website designed to communicate services, expertise, and lead generation.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square','fab fa-elementor']
            },
            {
              projectimg:'../img/crbn.jpg',
              projecttitle:'CarbonTrack UK',
              projecttype:'Corporate Website',
              projectyear:'2020',
              projectposition:'Lead Developer',
              projectlink:'https://carbontrackuk.co.uk/',
              projectsummary:'Sustainability and carbon management website focused on trust, clarity, and business credibility.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
            },
            {
              projectimg:'../img/dqtsi.jpg',
              projecttitle:'DynaQuest',
              projecttype:'Corporate Website',
              projectyear:'2020',
              projectposition:'Lead Developer',
              projectlink:'https://dqtsi.com/',
              projectsummary:'Corporate business website built around clearer messaging, stronger brand presence, and service positioning.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
            },
            {
              projectimg:'../img/sit.jpg',
              projecttitle:'Situp PH',
              projecttype:'Informative Website',
              projectyear:'2019',
              projectposition:'Lead Developer',
              projectlink:'https://dqtsi.com/',
              projectsummary:'Informational brand website designed to improve clarity, communication, and audience engagement.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
            },
            {
              projectimg:'../img/sha.jpg',
              projecttitle:'ShawarmaHouse PH',
              projecttype:'Informative Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://www.shawarmahouseph.com/',
              projectsummary:'Restaurant website focused on menu clarity, convenience, and stronger customer engagement.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
            },
            {
              projectimg:'../img/tgs.jpg',
              projecttitle:'The Greencross Saga',
              projecttype:'Informative Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://www.thegreencrosssaga.com/',
              projectsummary:'Informational website built around storytelling, readability, and clearer brand communication.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
            },
            {
              projectimg:'../img/comark.jpg',
              projecttitle:'Comark PH',
              projecttype:'E-Commerce Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://comark.com.ph/',
              projectsummary:'Retail business website designed to improve product visibility and customer browsing experience.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
            },
            {
              projectimg:'../img/tyd.jpg',
              projecttitle:'TYD Automotive AU',
              projecttype:'E-Commerce Website',
              projectyear:'2018',
              projectposition:'Lead Developer',
              projectlink:'https://tydautomotive.com.au/',
              projectsummary:'Automotive business website focused on product clarity, browsing ease, and stronger customer conversion.',
              projecthosting:'Apache / cPanel',
              projectstack:['fab fa-wordpress','fab fa-php','fab fa-html5','fab fa-css3-alt','fab fa-sass','fab fa-bootstrap','fab fa-js-square']
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
      title:'Feel free to reach out!',
      subtitle:'',
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


