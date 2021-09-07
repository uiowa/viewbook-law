<template>
<div :class="getStatClasses()">
  <template v-for="(stat, index) in stats" :key="index">
    <stat
      :headline="stat.headline"
      :headline_prefix="stat.headline_prefix"
      :headline_suffix="stat.headline_suffix"
      :stat_description="stat.stat_description"
      :stat_content="stat.stat_content"
      :stat_vertical="stat.stat_vertical"
    />
  </template>
</div>
</template>

<script>

import Stat from './Stat.vue';
export default {
    name: "statWrapper",

    props: {
      stat_classes: {
        type: String
      },
      stats: {
        /*
          Array of items with the following structure:
          {
            headline: String,
            headline_prefix: String,
            headline_suffix: String,
            stat_description: String,
            stat_content: String,
            stat_vertical: Boolean,
          },
        */
        type: Array
      },
    },
    components: {
      Stat
    },
    methods: {
      /*
          Adds any extra classes to the default necessary classes for a statWrapper.
      */
      getStatClasses() {
        let stat_classes = this.$props.stat_classes ? this.$props.stat_classes : '';
        let classes = "stat__wrapper bg--black " + stat_classes;
        return classes;
      }
    }
}
</script>