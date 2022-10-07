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
    banner_text='<p>Explore the breadth of the profession, excel in a legal landscape that fits your goals, and contribute to real change in society. With an Iowa Law degree, you can succeed anywhere.</p>'
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
    <div class="v-dots-scroll-target" id="success"></div>
  </div>
  <statWrapper
    :stats="stats_1"
  />

  <grid-panel
    link_url= 'https://law.uiowa.edu/academics'
    image= 'images/viewbook/2.jpg'
    headline= 'Success by the numbers'
    button_text= 'View our Curriculum'
    button_link= 'https://law.uiowa.edu/academics'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-image-left'
    grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
    grid_content_position= 'second'
    grid_panel_content= '<p>Iowa Law offers a unique opportunity to learn and interact in an intimate collegial setting. Our smaller class sizes allow students to work together and partner with experts across campus in fields such as engineering and health care to broaden their legal perspectives. Our faculty maintain an “open-door” policy where conversations extend beyond course material and into a student’s long-term goals. So when you ask for a letter of recommendation, you can be sure it will stand out—not only for its authenticity, but because it comes from someone who truly knows you.</p>'
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="real"></div>
  </div>

  <grid-panel
    link_url= 'https://law.uiowa.edu/experiential-learning'
    image= 'images/viewbook/4.jpg'
    headline= 'Take Real Action and make real change'
    button_text= 'Explore Experiential Opportunities'
    button_link= 'https://law.uiowa.edu/experiential-learning'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
    grid_panel_second_column= 'grid-panel__column-image-right'
    grid_content_position= 'first'
    grid_panel_content= '<p>At Iowa law, you’ll connect theory and practice to gain the competence to succeed in any legal setting. Starting your first year, you’ll learn how to model your legal skills to meaningfully assist members of the community. By your second or third year, you’ll gain real-world experience in research, litigation, transactional work, and policy advocacy. Our unique approach to hands-on learning through pro bono projects, simulation activities, clinics, and field placement programs will prepare you for a dynamic legal career.</p>'
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
    grid_panel_first_column= 'grid-panel__column-image-left'
    grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
    grid_content_position= 'second'
    grid_panel_content= '<p>Iowa Law boasts an experienced, student-centered faculty dedicated to the development of practice-ready lawyers. They bring extensive practical experience to the classroom, having clerked for federal judges and practiced law in government, business, and at private firms. With an 8:1 student-to-faculty ratio and an “open-door” policy, our faculty foster a personalized approach to learning and a dynamic legal curriculum.</p>'
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="writing"></div>
  </div>

  <grid-panel
    link_url= 'https://law.uiowa.edu/experiential-learning/legal-writing'
    image= 'images/viewbook/5.jpg'
    headline= 'Unmatched writing resources to help you stand out'
    button_text= 'Learn about Legal Writing'
    button_link= 'https://law.uiowa.edu/experiential-learning/legal-writing'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
    grid_panel_second_column= 'grid-panel__column-image-right'
    grid_content_position= 'first'
    grid_panel_content= '<p>Iowa Law has long been at the forefront of a legal writing education. We invest in full-time writing faculty—and we are one of the few top-tier law schools to do so. During your first year, you’ll engage in small-section writing courses and receive one-on-one instruction from your professors. Throughout your second and third years, you’ll have countless opportunities to gain valuable writing experience, refine your skills, and build the confidence you need to stand out in a competitive workforce.</p>'
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="best"></div>
  </div>

  <grid-panel
    link_url= 'https://law.uiowa.edu/student-experience/student-life/iowa-city'
    image= 'images/viewbook/6.jpg'
    headline= 'The Best College Town'
    button_text= 'Discover Iowa City'
    button_link= 'https://law.uiowa.edu/student-experience/student-life/iowa-city'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-image-left'
    grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
    grid_content_position= 'second'
    grid_panel_content= '<p>Considered one of the best places to live in the country, Iowa City offers big-city amenities alongside the comfort and affordability of a small town. Where downtown seamlessly blends with the heart of campus, you’ll find more than 100 restaurants, BIG Ten athletics, and a dynamic art scene all within walking distance from the Boyd Law Building. And with annual festivals, block parties, and plenty of exciting events scheduled throughout the year, you’ll find it easy to balance the rigors of law school with fun and new experiences.</p>'
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="career"></div>
  </div>

  <grid-panel
    link_url= 'https://law.uiowa.edu/careers'
    image= 'images/viewbook/7.jpg'
    headline= 'Career Advice that gets you hired'
    button_text= 'View Career Services'
    button_link= 'https://law.uiowa.edu/careers'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
    grid_panel_second_column= 'grid-panel__column-image-right'
    grid_content_position= 'first'
    grid_panel_content= '<p>Beginning your first semester, Iowa Law will provide you with valuable resources and personalized assistance to help you prepare for a successful career. From on-campus interviews to guidance with résumés and cover letters, you’ll have the support you need to practice law in any field, anywhere. You’ll also be welcomed into a network of 10,700+ Iowa Law alumni—many of whom recruit current Iowa Law students or will connect you to prospective employers.</p>'
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


  <div class="grid--fourcol--25">
    <div class="list-container">
      <Card
        image="images/viewbook/barbi-rodriguez.jpg"
        title="Connect theory to practice<br /><b>Barbi Rodriguez</b>"
        author="Class of 2022"
        content='<b>Most Rewarding Law School Experience:</b> "The experiential learning opportunities at Iowa Law broadened my sense of what my career could comprise while letting me experience varied approaches to lawyering, advocacy, service, and mentorship. I entered law school with an interest in practicing public interest immigration law, but I had not internalized the many forms this could take. The semesters I spent with the Community Empowerment Law Project and the Immigration Advocacy Clinic were especially impactful in helping me clarify the kind of lawyer I want to be. It meant a lot to serve the needs of individuals and families who were evacuated from Afghanistan and are resettling in eastern Iowa."<br>
        <b>What’s Ahead:</b> Clerking for the United States District Court of the Eastern District of New York, then returning to Iowa to clerk for the United States Court of Appeals for the Eighth Circuit.'
        class="card--stacked card--centered-left card--alignment-left card--padded"
        media_class="card__media--large card__media card__media"
        img_class=""
        headline_class="h3 headline headline--uppercase"
        headline_url_class="click-target"
      />
      <Card
        image="images/viewbook/marcus-weymiller.jpg"
        title="Learn in an intimate collegial setting<br /><b>Marcus Weymiller</b>"
        author="Class of 2022"
        content='<b>Most Rewarding Law School Experience:</b> "I really enjoyed learning from all the smart, driven, and gracious faculty at Iowa Law, especially Professor Muller. Not only did I learn a lot about the law, but I learned what it means to invest in your legal career and the people around you. Professor Muller gives his all to every project he is a part of and treats everyone with such dignity and respect. He has been very instrumental in my professional development, and I’m grateful to have him as a mentor."<br>
        <b>What’s Ahead:</b> Clerking for Justice G. Barry Anderson at the Minnesota Supreme Court.'
        class="card--stacked card--centered-left card--alignment-left card--padded"
        media_class="card__media--large card__media card__media"
        img_class=""
        headline_class="h3 headline headline--uppercase"
        headline_url_class="click-target"
      />
      <Card
        image="images/viewbook/lauren-knudson.jpg"
        title="Communicate with confidence<br /><b>Lauren Knudson</b>"
        author="Class of 2022"
        content='<b>Most Rewarding Law School Experience:</b> "During my time as editor-in-chief of the Iowa Law Review, I gained a ton of valuable writing experience that helped me prepare for my future career, especially in the editing and publication process. The position not only sharpened my leadership skills, but also gave me the confidence to publish a piece of my own. I can honestly say I would not have the clerkship or the job I have lined up in Washington, D.C., without the writing opportunities at Iowa Law."<br>
        <b>What’s Ahead:</b> Joining Mayer Brown’s litigation team in Washington, D.C., with a focus on antitrust.'
        class="card--stacked card--centered-left card--alignment-left card--padded"
        media_class="card__media--large card__media card__media"
        img_class=""
        headline_class="h3 headline headline--uppercase"
        headline_url_class="click-target"
      />
      <Card
        image="images/viewbook/seung-woo-ban.jpg"
        title="Align practical skills and career goals<br /><b>Seung Woo Ban</b>"
        author="Class of 2024"
        content='<b>Most Rewarding Law School Experience:</b> "As a nontraditional law student with over a decade of work experience, it’s important for me to clearly understand what I want to do with my JD degree upon graduation. Iowa Law’s career advisors were really helpful in finding my summer internship in L.A. They’ve also been helping me navigate through various career possibilities in the U.S. and around the world. I also regularly attended events hosted by the Career Services Office, which has allowed me to get a solid understanding of specific legal practice areas."<br>
        <b>What’s Ahead:</b> Working as a summer associate to experience a different firm culture and/or practice area than his previous associate position at Ford Harrison LLP in Los Angeles.'
        class="card--stacked card--centered-left card--alignment-left card--padded"
        media_class="card__media--large card__media card__media"
        img_class=""
        headline_class="h3 headline headline--uppercase"
        headline_url_class="click-target"
      />
    </div>
  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="anywhere"></div>
  </div>

  <statWrapper
    :stats="stats_2"
    stat_classes="no--hover"
  />

  <banner
    image="images/viewbook/8.jpg"
    banner_size="large"
    banner_vertical_alignment="vertical-center"
    banner_horizontal_alignment="horizontal-center"
    banner_classes=""
    banner_type="image"
    banner_overlay= "gradient-bottom"
    banner_text='<p>Iowa Law is an ideal place to study law: small enough that your professors will know you well, yet large enough to be nationally renowned and a launchpad for opportunity. With an Iowa Law degree, you’ll be prepared to practice law anywhere around the world. From private firms and Fortune 100 companies to global nonprofits and government agencies, you’ll find that Iowa alumni aren’t just in Iowa, they’re everywhere.</p>'
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
          stat_description: 'BEST LAW SCHOOL BY <i style="display: block">U.S. NEWS & WORLD REPORT</i>',
          stat_content: 'Among 193 nationally ranked law schools.',
        },
        {
          headline: '99',
          headline_prefix: '',
          headline_suffix: '%',
          stat_description: 'JOB PLACEMENT RATE WITHIN 10 MONTHS OF GRADUATION',
          stat_content: '16% higher than the national average.',
        },
        {
          headline: 'Best',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'VALUE LAW SCHOOL FOR 8 CONSECUTIVE YEARS BY THE <i>NATIONAL JURIST</i>',
          stat_content: 'Based on tuition costs, bar passage rates, and employment success.',
        },
        {
          headline: '84',
          headline_prefix: '',
          headline_suffix: '%',
          stat_description: 'BAR PASSAGE RATE AMONG FIRST-TIME TAKERS',
          stat_content: 'Nearly 5% higher than the national average.',
        }
      ],
      stats_2: [
        {
          headline: '10,700',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'ALUMNI IN ALL 50 STATES and 43 countries',
          stat_content: '',
        },
        {
          headline: '25',
          headline_prefix: '',
          headline_suffix: '%',
          stat_description: 'of the class of 2021 earned state or federal clerkships across the country',
          stat_content: '',
        },
        {
          headline: '190',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'EMPLOYERS COME TO CAMPUS each year for on campus interviews',
          stat_content: '',
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
          section_id: 'success'
        },
        {
          section_title: 'TAKE REAL ACTION AND MAKE REAL CHANGE',
          section_id: 'real'
        },
        {
          section_title: 'LEARN FROM EXPERT LEGAL SCHOLARS',
          section_id: 'learn'
        },
        {
          section_title: 'UNMATCHED WRITING RESOURCES TO HELP YOU STAND OUT',
          section_id: 'writing'
        },
        {
          section_title: 'THE BEST COLLEGE TOWN',
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

.grid-panel__content .headline--uppercase {
  font-size: calc(2.5em + .9vw) !important;
}

@media (max-width: 93.75em) and (min-width: 84.375em) {
  .grid-panel--asymmetrical p {
    font-size: 1em;
  }
}

// Stat fix to avoid inconsistent stacking below container breakpoint.
@media (max-width: 81.375em) and (min-width: 768px) {
  .stat--horizontal:not(.element--flex-center) .stat__description {
    flex-basis: 80%;
  }
  .stat--horizontal:not(.element--flex-center) .stat__content {
    flex-basis: 80%;
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

.banner p {
  @include breakpoint(sm) {
    font-size: 1.4rem;
  }
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

.no--hover .stat__grid {
  cursor: default;
  p.stat__content {
    padding-top: 0;
    margin-top: 0;
    border-top: none;
    flex-basis: 0%;
  }
}

.grid--fourcol--25 {
  .list-container {
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: 1fr;
    gap: 0;
    @include breakpoint(sm) {
      grid-template-columns: repeat(auto-fill, minmax(46.7%, 1fr));
    }
    @include breakpoint(container) {
      grid-template-columns: repeat(auto-fill, minmax(21%, 1fr));
    }
  }
}

</style>
