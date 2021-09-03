<template>
<!-- This template should give enough examples of what Vue components should look like.-->
<!-- Notable example sections should have comments to help anyone new to the system understand them. -->
<iowa-bar
  iowa_bar_classes="iowa-bar--narrow"
  site_name="College of Law"
  site_name_link="https://law.uiowa.edu"
/>

<!-- This is an example of a vertical dots scroll spacer, -->
<!-- Which is what the vertical dots menu will jump to when the corresponding dot is clicked -->
<!-- The ID of the `v-dots-scroll-target` and its corresponding `section_id` in the `sections` array should match -->
<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="hero-banner"></div>
</div>

<banner
  image="images/viewbook/1.jpg"
  banner_size="large"
  banner_vertical_alignment="vertical-center"
  banner_horizontal_alignment="horizontal-center"
  banner_classes="lighter-gradient"
  banner_type="image"
  banner_overlay= "gradient-bottom"
  banner_text='<p>World-class academics, close connections with faculty, collaborative culture, dynamic campus life, and invaluable resources to help you prepare for a career you love.</p>'
  banner_title='This is <span>Iowa Law</span>'
  banner_title_classes='headline headline--uppercase'
/>

<div role="region" class="menu-group__wrapper">
  <div class="menu-group__container">
    <menuGroup
      :items="menu_items"
    />
  </div>
</div>

<verticalDots
  :sections="sections"
/>

<!-- This is a great example of passing `props` in to a component inline. -->
<!-- Anything that will be used as a String in the component can be written without a colon before it. -->
<!-- Anything that does not (eg. Boolean, int, float) must have a colon in front of it. -->
<!-- This tells Vue that it should evaluate it like a javascript variable. -->
<!-- <stat
  headline="34"
  headline_prefix="#"
  headline_suffix=""
  stat_description="BEST PUBLIC UNIVERSITY BY U.S. NEWS & WORLD REPORT"
  stat_content="Among the top 2% of universities worldwide."
  :stat_vertical="true"
/> -->

<!-- This is a great example of passing props from the `data() { return { PROPS }}` area further down in this file.-->
<!-- You can define props there to pass to any component. -->
<!-- However, you must prefix every component used this way with a colon. -->
<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="stats"></div>
</div>
<statWrapper
  :stats="stats_1"
/>

<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="stand"></div>
</div>

<grid-panel
  link_url= 'https://law.uiowa.edu/academics'
  image= 'images/viewbook/2.jpg'
  headline= 'Stand Out from the crowd'
  button_text= 'View our Curriculum'
  button_link= 'https://law.uiowa.edu/academics'
  grid_panel_type= 'grid-panel grid-panel--asymmetrical'
  grid_panel_first_column= 'grid-panel__column-image-left'
  grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
  grid_content_position= 'second'
  grid_panel_content= '<p>Iowa Law offers a unique opportunity to learn and interact in an intimate collegial setting. Our smaller class sizes allow students to work together and partner with experts across campus in fields such as engineering and health care to broaden their legal perspectives. Our faculty maintain an “open-door” policy where conversations extend beyond course material and into a student’s long-term goals. So when you ask for a letter of recommendation, you can be sure it will stand out—not only for its authenticity, but because it comes from someone who truly knows you.</p>'
/>

<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="learn"></div>
</div>

<grid-panel
  link_url= 'https://law.uiowa.edu/faculty-and-scholarship'
  image= 'images/viewbook/3.jpg'
  headline= 'Learn from expert legal scholars'
  button_text= 'Meet our Faculty'
  button_link= 'https://law.uiowa.edu/faculty-and-scholarship'
  grid_panel_type= 'grid-panel grid-panel--asymmetrical'
  grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
  grid_panel_second_column= 'grid-panel__column-image-right'
  grid_content_position= 'first'
  grid_panel_content= '<p>Iowa boasts an experienced, student-centered faculty dedicated to the development of practice-ready lawyers. Their expertise translates into engaging coursework across the legal spectrum¬, from corporate and business law to international law and property law. As the best public university for writing in the U.S., our faculty are dedicated to developing your skills in research, analytical thinking, and persuasive communication¬– skills you can bring with you not only to the practice of law, but to any career.</p>'
/>

<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="take"></div>
</div>

<grid-panel
  link_url= 'https://law.uiowa.edu/experiential-learning'
  image= 'images/viewbook/4.jpg'
  headline= 'Take Real Action and make real change'
  button_text= 'Explore Experiential Opportunities'
  button_link= 'https://law.uiowa.edu/experiential-learning'
  grid_panel_type= 'grid-panel grid-panel--asymmetrical'
  grid_panel_first_column= 'grid-panel__column-image-left'
  grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
  grid_content_position= 'second'
  grid_panel_content= '<p>At Iowa Law, you’ll learn first-hand how to be an effective problem-solver in an everchanging society. Starting from day 1, you’ll learn how to model your legal skills to meaningfully assist members of the community. By your second or third year, you’ll have the ability to represent individuals in litigation, transactional work, and policy advocacy. From semester-long placement programs to moot court competitions, you’ll find endless opportunities to master your professional skills while gaining confidence to begin your career.</p>'
/>


<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="best"></div>
</div>

<grid-panel
  link_url= 'https://law.uiowa.edu/student-experience/student-life/iowa-city'
  image= 'images/viewbook/5.jpg'
  headline= 'The Best Place to live'
  button_text= 'Discover Iowa City'
  button_link= 'https://law.uiowa.edu/student-experience/student-life/iowa-city'
  grid_panel_type= 'grid-panel grid-panel--asymmetrical'
  grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
  grid_panel_second_column= 'grid-panel__column-image-right'
  grid_content_position= 'first'
  grid_panel_content= '<p>Iowa City is considered one of the best places to live in the country. With big-city amenities and the comfort of a small town, members of our community reap the best of both worlds. Where downtown seamlessly blends with the heart of campus, you’ll find hundreds of restaurants, BIG Ten athletics, and a dynamic art scene all within walking distance from the Boyd Law Building. And with annual festivals, block parties, and plenty of exciting events scheduled throughout the year, you’ll find it easy to balance the rigors of law school with fun and new experiences.</p>'
/>


<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="career"></div>
</div>

<grid-panel
  link_url= 'https://law.uiowa.edu/careers'
  image= 'images/viewbook/6.jpg'
  headline= 'Career Advice that gets you hired'
  button_text= 'Learn About Career Services'
  button_link= 'https://law.uiowa.edu/careers'
  grid_panel_type= 'grid-panel grid-panel--asymmetrical'
  grid_panel_first_column= 'grid-panel__column-image-left'
  grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
  grid_content_position= 'second'
  grid_panel_content= '<p>Beginning your first semester, Iowa Law will provide you with the resources and support you’ll
need to succeed in the professional world. You’ll learn how to develop résumé, emphasize your strengths, and identify possibilities that align with your career goals. Our dedicated career counselors will help you navigate your job search, explore your options, and arrange valuable opportunities to connect with prospective employers both on campus and around the world.</p>'
/>

<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="hawkeyes"></div>
</div>

<banner
  image=""
  banner_size="small"
  banner_vertical_alignment="vertical-center"
  banner_horizontal_alignment="horizontal-center"
  banner_classes="bg--gold--pattern--brain brain banner--slim-title"
  banner_type=""
  banner_overlay= ""
  banner_text=''
  banner_title='See what students are saying about Iowa Law'
  banner_title_classes='headline headline--uppercase'
/>


<div class="grid--threecol--33-34-33">
  <div class="list-container">
    <Card
      image="images/viewbook/hayleigh-hansen.JPG"
      title="Specialize in your interests<br /><b>Hayleigh Hansen-Boardman</b>"
      author="Juris Doctor, '21"
      content="
        'I wanted to see health law from the client’s perspective. Getting to interact with patients and medical providers for a week was absolutely invaluable. I would honestly say that experience was the single-most practical learning experience I had throughout my legal education.'
      "
      class="card--stacked card--centered-left card--alignment-left card--padded"
      media_class="card__media--large card__media card__media"
      img_class=""
      headline_class="h3 headline headline--uppercase"
      headline_url_class="click-target"
      link_url="https://law.uiowa.edu/news/2020/04/iowa-law-where-law-and-health-care-meet"
      link_title="See full story"
    />
    <Card 
      image="images/viewbook/kayla-boyd.jpg"
      title="Turn passion into experience<br /><b>Kayla Boyd</b>"
      author="Juris Doctor, '21"
      content="
        'My goal is to help the most vulnerable people in our criminal legal system, and the best way to do that is to provide an outstanding legal defense for those who have been wrongfully accused and treated unfairly, to stand up in court and tell their story.'
      "
      class="card--stacked card--centered-left card--alignment-left card--padded"
      media_class="card__media--large card__media card__media"
      img_class=""
      headline_class="h3 headline headline--uppercase"
      headline_url_class="click-target"
      link_url="https://stories.uiowa.edu/spring-2021-graduates-kayla-boyd"
      link_title="See full story"
    />
    <Card 
      image="images/viewbook/emani-marshall.jpg"
      title="Build a foundation for your career<br /><b>Emani Marsall-Loving</b>"
      author="Juris Doctor, '21"
      content="
        'While writing my brief and preparing for oral arguments, I realized that Iowa Law had equipped me with the necessary skills to excel. Participating in the Appellate Advocacy program made me more confident, prepared, and equipped to take on the legal world and my legal career.'
      "
      class="card--stacked card--centered-left card--alignment-left card--padded"
      media_class="card__media--large card__media card__media"
      img_class=""
      headline_class="h3 headline headline--uppercase"
      headline_url_class="click-target"
      link_url="https://law.uiowa.edu/news/2020/12/midwest-travels-take-marshall-loving-iowa-supreme-court"
      link_title="See full story"
    />
  </div>
</div>

<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" id="anywhere"></div>
</div>

<statWrapper
  :stats="stats_2"
/>

<banner
  image="images/viewbook/7.jpg"
  banner_size="large"
  banner_vertical_alignment="vertical-center"
  banner_horizontal_alignment="horizontal-center"
  banner_classes=""
  banner_type="image"
  banner_overlay= "gradient-bottom"
  banner_text='<p>Iowa Law is an ideal place to study law: small enough that your professors will know you well, yet large enough to be a launchpad for opportunity. With an Iowa Law degree, you’ll be prepared to practice law anywhere around the world. From private firms and Fortune 100 companies to global nonprofits and government agencies, you’ll find that Iowa alumni aren’t just in Iowa, they’re everywhere.</p>'
  banner_title='First Iowa <span>then anywhere</span>'
  banner_title_classes='headline headline--uppercase'
/>




<footerSection
  site_name="College of Law"
  site_name_link="https://law.uiowa.edu/"
  :contact_info="contact_info"
  :social_media_links="social_media_links"
/>

</template>

<script>
// In order to use components, you must import them from their files to your script.
// You must also register them in the `components` section of the `export default {}` area below.
// For ease of use, all currently usable components are imported here.
import Banner from './components/Banner.vue';
import Card from './components/Card.vue';
import Stat from './components/Stat.vue';
import statWrapper from './components/statWrapper.vue';
import IowaBar from './components/IowaBar.vue';
import GridPanel from './components/GridPanel.vue';
import Headline from './components/Headline.vue';
import verticalDots from './components/verticalDots.vue';
import linkButton from './components/linkButton.vue';
import Aerial from './components/Aerial.vue';
import menuGroup from './components/menuGroup.vue';
import footerSection from './components/footerSection.vue';
import Modal from './components/Modal.vue';
import SiteName from './components/siteName.vue';

export default {
  name: 'App',

  // In addition to importing all components from their files, you must register them here for them to work.
  components: {
    Banner,
    Card,
    Stat,
    statWrapper,
    IowaBar,
    Headline,
    verticalDots,
    GridPanel,
    linkButton,
    Aerial,
    menuGroup,
    Modal,
    footerSection,
    SiteName
  },

  // This area is where we are currently importing the set props for our components.
  data() {
    return {
      stats_1: [
        {
          headline: '29',
          headline_prefix: '#',
          headline_suffix: '',
          stat_description: 'BEST LAW SCHOOL BY U.S. NEWS & WORLD REPORT',
          stat_content: 'Among 193 nationally ranked law schools.',
        },
        {
          headline: '100',
          headline_prefix: '',
          headline_suffix: '%',
          stat_description: 'JOB PLACEMENT RATE WITHIN 10 MONTHS OF GRADUATION',
          stat_content: '10% higher than the national average.',
        },
        {
          headline: 'Best',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'VALUE LAW SCHOOL BY THE NATIONAL JURIST FOR 7 CONSECUTIVE YEARS',
          stat_content: 'Based on tuition costs, bar passage rates, and employment success.',
        },
        {
          headline: '94',
          headline_prefix: '',
          headline_suffix: '%',
          stat_description: 'BAR PASSAGE RATE PASSAGE RATE AMONG FIRST-TIME TAKERS',
          stat_content: '13% higher than the national average.',
        }
      ],
      stats_2: [
        {
          headline: '10,500',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'ALUMNI IN ALL 50 STATES',
          stat_content: 'And 43 countries',
        },
        {
          headline: '9',
          headline_prefix: '',
          headline_suffix: 'th',
          stat_description: 'HIGHEST EMPLOYMENT RATE',
          stat_content: 'For full-time jobs by law.com',
        },
        {
          headline: '100',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'EMPLOYERS COME TO CAMPUS',
          stat_content: 'Each year for on campus interviews',
        }
      ],
      menu_items: [
        {
          text: 'Apply',
          url: 'https://law.uiowa.edu/apply',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--apply'
        },
        {
          text:  'Visit',
          url: 'https://law.uiowa.edu/admissions/admissions-events',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--visit'
        },
        {
          text: 'Contact',
          url: 'https://law.uiowa.edu/admissions/contact-us',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--ask'
        },
        {
          text: 'Request Info',
          url: 'https://law.uiowa.edu/admissions/request-information',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--connect'
        },
      ],
      sections: [
        {
          section_title: 'Back to Top',
          section_id: 'hero-banner'
        },
        {
          section_title: 'SUCCESS BY THE NUMBERS',
          section_id: 'stats'
        },
        {
          section_title: 'STAND OUT FROM THE CROWD',
          section_id: 'stand'
        },
        {
          section_title: 'LEARN FROM EXPERT LEGAL SCHOLARS',
          section_id: 'learn'
        },
        {
          section_title: 'TAKE REAL ACTION AND MAKE REAL CHANGE',
          section_id: 'take'
        },
        {
          section_title: 'THE BEST PLACE TO LIVE',
          section_id: 'best'
        },
        {
          section_title: 'CAREER ADVICE THAT GETS YOU HIRED',
          section_id: 'career'
        },
        {
          section_title: 'WHAT ARE HAWKEYES SAYING?',
          section_id: 'hawkeyes'
        },
        {
          section_title: 'FIRST IOWA THEN ANYWHERE',
          section_id: 'anywhere'
        },
      ],
      contact_info: '<p>280 Boyd Law Building<br />Iowa City, Iowa 52242<br><a href="tel:13193359034"><i class="fas fa-phone"></i> 319-335-9034</a><br /></p>',
      social_media_links: [
        {
          text: 'Facebook',
          url: 'https://www.facebook.com/IowaLawSchool',
          icon_class: 'fab fa-facebook-square'
        },
        {
          text: 'Instagram',
          url: 'https://www.instagram.com/uiowalawschool',
          icon_class: 'fab fa-instagram'
        },
        {
          text:  'Twitter',
          url: 'https://twitter.com/IowaLawSchool',
          icon_class: 'fab fa-twitter-square'
        },
        {
          text:  'LinkedIn',
          url: 'https://www.linkedin.com/school/university-of-iowa-college-of-law',
          icon_class: 'fab fa-linkedin'
        }
      ]
    }
  },
  mounted() {
    let clickA11y = document.createElement('script')
    clickA11y.setAttribute('src', '/js/click-a11y.js')
    document.head.appendChild(clickA11y)
  },
}
</script>

<style lang="scss">
$imgpath: '../node_modules/@uiowa/uids/src/assets/images';
@import '../node_modules/@uiowa/uids/src/assets/scss/reset.scss';
@import '../node_modules/@uiowa/uids/src/components/typography/lists/lists.scss';
@import '../node_modules/@uiowa/uids/src/components/tables/tables.scss';
@import '../node_modules/@uiowa/uids/src/components/typography/paragraph/paragraph.scss';
@import '../node_modules/@uiowa/uids/src/components/colors/colors.scss';
@import '../node_modules/@uiowa/uids/src/components/grid/grid.scss';
@import '../node_modules/@uiowa/uids/src/components/viewbook/grid-panel/grid-panel.scss';
@import '../node_modules/@uiowa/uids/src/components/card/card.scss';
@import '../node_modules/@uiowa/uids/src/components/media/media.scss';
@import '../node_modules/@uiowa/uids/src/components/background/background.scss';
@import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook.scss';

.image-grid__section {
  line-height: 0;
}

.headline__text b {
  color: $grey;
  font-weight: normal;
}

@media (min-width: 992px) {
  .banner p {
    width: 60%;
    margin: 0 auto;
  }
}

@media (max-width: 768px) and (min-width: 0) {
  .menu-group__wrapper .menu-item:not(:last-child) .bttn--outline {
    border-bottom: none;
  }
}

@media (max-width: 93.75em) and (min-width: 84.375em) {
  .grid-panel__content .headline--uppercase {
    font-size: calc(2.5em + .3vw) !important;
  }
}

.grid-panel__column-content-right.grid-panel__content, .grid-panel__column-content-left.grid-panel__content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 3rem 3.5rem 3rem 3rem;
}

.element--circle-list ul {
  margin-top: 1.05rem;
  margin-bottom: 1.05rem;
  margin-left: 1.875rem;
}

.banner__image img {
  filter: brightness(150%) saturate(150%);
}

.banner::after {
  background: rgba(0,0,0,.5);
}

@include breakpoint(sm) {
  .banner--gradient-bottom::after {
    background: linear-gradient(180deg,transparent 0,rgba(0,0,0,.65) 70%);
  }

  .banner--gradient-bottom.lighter-gradient::after {
    background: linear-gradient(180deg, transparent 0, rgba(0, 0, 0, 0.37) 70%);
  }
}

.card {
  p {
    margin-top: 0.625rem;
  }

  &--padded .card__body {
    padding: 2rem;
  }
}

.bg--gold--pattern--brain .headline__text {
  color: black;
}

// Override and condense for smaller devices.
.menu-group__wrapper {
  transition: padding 0.5s ease;
  padding: 0.3rem 0;
  .menu-group__container .menu a {
    transition: margin 0.5s ease;
    margin: 0px .5rem;
    padding-bottom: 0.5rem;
  }
  .bttn--outline {
    border: none;
  }
}
@media (min-height: 1000px) {
  .menu-group__wrapper {
    padding: 1.875rem 0;
    .menu-group__container .menu a {
      margin: 0px 1.05rem;
    }
    .bttn--outline {
      border: 1px solid rgb(21, 21, 21);
    }
  }

  .card {
    border: none;
  }
}
</style>
