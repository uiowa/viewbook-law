<template>
  <header class="iowa-bar" :class="IowaBarClasses()">
    <div class="iowa-bar__container">
      <logo
        logo_id="header"
        logo_classes="logo--tab"
      />
      <siteName 
        :site_name="site_name"
        :site_name_link="site_name_link"
      />
      <!-- This is where we would print Top links -->
      <!-- This is where we would print off canvas -->
    </div>
    <!-- this is where we would print below bar content -->
  </header>
</template>

<script>
import Logo from './Logo.vue';
import siteName from './siteName.vue';

export default {
    name: 'IowaBar',

    props: {
      iowa_bar_classes: {
        type: String
      },
      parent_site: {
        type: String
      },
      site_name: {
        type: String
      },
      site_name_link: {
        type: String
      }
    },

    components: {
      Logo,
      siteName
    },

    methods: {
      // This method will default the iowa bar to narrow if there is a parent site set.
      IowaBarClasses() {
        if (typeof this.$props.parent_site !== "undefined" ) {
          return (this.$props.iowa_bar_classes + ' ' + 'iowa-bar--narrow');
        }
        else {
          return this.$props.iowa_bar_classes;
        }
      }
    }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/branding/iowa-bar/iowa-bar.scss';
</style>