<template>
  <div
    class="post-card content-box"
    :class="{ 'post-card--has-poster': post.poster }"
  >
    <!-- <div class="post-card__header">
      <g-image alt="Cover image" v-if="post.cover_image" class="post-card__image" :src="post.cover_image" />
    </div> -->
    <div class="post-card__content">
      <g-link class="post-card__link" :to="post.path">
        <h2 class="post-card__title" v-html="post.title" />
      </g-link>
      <PostMeta class="post-card__meta" :post="post" />

      <p class="post-card__description" v-html="post.description" />

      <PostTags class="post-card__tags" :post="post" />
    </div>
  </div>
</template>

<script>
import PostMeta from "~/components/PostMeta";
import PostTags from "~/components/PostTags";

export default {
  components: {
    PostMeta,
    PostTags,
  },
  props: ["post"],
};
</script>

<style lang="scss">
.post-card {
  margin-bottom: var(--space);
  position: relative;
  max-width: var(--content-width);
  margin: 0 auto;
  padding: var(--space);

  // &__header {
  //   margin-left: calc(var(--space) * -1);
  //   margin-right: calc(var(--space) * -1);
  //   // margin-bottom: calc(var(--space) / 2);
  //   margin-top: calc(var(--space) * -1);
  //   overflow: hidden;
  //   // border-radius: var(--radius) var(--radius) 0 0;

  //   &:empty {
  //     display: none;
  //   }
  // }

  // &__image {
  //   min-width: 100%;
  // }

  &__title {
    margin-top: 0;
    // margin-bottom: 0.3em;
    font-size: 1.3em;
  }

  // &:hover {
  //   transform: translateY(-5px);
  //   box-shadow: 1px 10px 30px 0 rgba(0,0,0,.1);
  // }

  &__meta {
    margin: 1em 0;
  }

  &__tags {
    z-index: 1;
    margin: 1em 0;
    position: relative;
  }

  &__link {
    text-decoration: none;
    // &:hover {
    //   color: inherit;
    // }
  }

  // &__link {
  //   position: absolute;
  //   top: 0;
  //   left: 0;
  //   width: 100%;
  //   height: 100%;
  //   opacity: 1.0;
  //   overflow: hidden;
  //   text-indent: -9999px;
  //   z-index: 0;
  // }
}
</style>
