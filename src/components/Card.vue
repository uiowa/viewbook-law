<template>
    <div class="card" :class="class">
        <div v-if="image" class="card__media" :class="media_class">
            <a v-if="link_element == 'image'" :href="link_url">
                <img class="card__img" :class="img_class" :src="image" alt="Alt Text" loading="lazy">
            </a>
            <img v-else class="card__img" :class="img_class" :src="image" alt="Alt Text" loading="lazy">
        </div>

        <div class="card__body">
            <Headline
                v-if="title"
                headline_level="h2"
                class="card__title"
                :headline_class="headline_class"
                :headline="title"
                :headline_url="link_url"
            />

            <div v-if="author!==''" class="card__author">{{ author }}</div>

            <p v-html="content"></p>

            <template v-if="link_url && show_button">
                <template v-if="link_element == 'button'">
                    <linkButton
                        :button_link = "link_url"
                        button_type = "bttn--full bttn--outline bttn--tertiary bttn--sans-serif"
                        :button_text = "link_title"
                        :button_icon = "true"
                    />
                </template>
                <template v-else>
                    <!-- This should eventually have JS attached o it to click the right thing. -->
                    <div aria-hidden="true" class="bttn bttn--full bttn--outline bttn--tertiary bttn--sans-serif" :id="aria!=='' ? aria :''">
                        {{ link_title }}
                        <i class="fas fa-arrow-right"></i>
                    </div>
                </template>
            </template>
        </div>
    </div>
</template>

<script>
import Headline from './Headline.vue';
import linkButton from './linkButton.vue';

export default {
    name: 'Card',
    props: {
        class: {
          type: String
        },
        media_class: {
          type: String
        },
        img_class: {
          type: String
        },
        headline_class: {
          type: String
        },
        image: {
            type: String
        },
        title: {
            type: String
        },
        link_url: {
            type: String
        },
        link_title: {
            type: String
        },
        aria: {
            type: String
        },
        author: {
            type: String
        },
        content: {
            type: String
        }
    },
    components: {
        Headline,
        linkButton,
    },
    data() {
      let data = {
        link_element: 'card',
        show_button: false,
      };

      // Set dynamic properties of link_element and show_button.
      if (this.link_url) {
          if (this.title) {
              data.link_element = 'title';

              // If we also have link text, then we'll show a psuedo-button.
              if (this.link_title) {
                  data.show_button = true;
              }
          }
          else if (this.link_title) {
            data.link_element = 'button';
            data.show_button = true;
          }
      }

      return data;
    },
    // This will attach a click listener on this card if it has one of the classes listed in 'link_elements'.
    // created() {
    //     this.$nextTick(() => {
    //         const element = this.$el;
    //         const link_elements = ['.card__title a', '.card__media a', 'a.bttn'];
    //         let up, down, link, i;
    //         // Check if it has one of the classes defined in 'link_elements'.
    //         for (i = 0; i < link_elements.length; i++) {
    //             if (link = element.querySelector(link_elements[i])) {
    //                 break;
    //             }
    //         }
    //         // If we have a match, attach behaviors.
    //         if (link) {
    //             element.style.cursor = 'pointer';
    //             element.onmousedown = () => down = +new Date();
    //             element.onmouseup = () => {
    //                 up = +new Date();
    //                 // Trigger click event if the click duration is short enough.
    //                 if ((up - down) < 200) {
    //                     link.click();
    //                 }
    //             }
    //         }
    //     });
    // },
}
</script>

<style lang="scss">
  @import '../../node_modules/@uiowa/uids/src/components/card/card.scss';

  [class*="bg--"] div[aria-hidden='true'] {
    color: inherit;
  }
</style>