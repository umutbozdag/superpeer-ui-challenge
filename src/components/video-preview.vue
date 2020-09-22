<template>
  <main id="video-settings" class="row justify-center">
    <section class="video-preview w-full">
      <div class="video-preview-wrapper">
        <video
          aria-describedby="call-hosted-by-user"
          class="video-preview-user brd-8"
          poster="https://s3-alpha-sig.figma.com/img/80b2/c8b9/db05a73b5f7cb33be5906f4d71d57593?Expires=1601251200&Signature=EMlA3~QQkzTQjy7TmQsjtT2CSZq0P8owfYw5z7m48j2niJ3bi6L8LPqT6iCw-i386tYZtHYQyvG3nWwBB1x8pwRWzIkU3giMNTlv3LMzGG7Hs5gbN9vb1OczBCL04-yykkOLgJK35Y2t~uNQJlmKOfnhrjR6cQVEEQ-fbK9KKsc96j3T65blH6nTd0f6aDm-qZ87EZDWnlsLsLeBwvIW6ORahfR85KtWhOZ4nd1~~QHkt5z0JLs7KoCVep5NQEApnh8ogdsb3PQfW4JG6xTNzd7qmYaBabqHmN3pb7T5sC5PAXvX4cmH6Rq-4qGCfUq~kV4Ebfj4iJ5sNA06ZU4lzw__&Key-Pair-Id=APKAINTVSUGEWH5XD5UA"
        >
          <p>
            Your browser doesn't support HTML5 video. Here is a
            <a
              href="https://www.youtube.com/watch?v=f6noiVByjzM"
            >link to the video</a> instead.
          </p>
        </video>
        <video-controls/>
      </div>
      <super-input
        name="call-user-name"
        class="mt-12"
        placeholder="Please enter a user name"
        value="Adem ilter"
        required
      >
        <template #icon>
          <i role="img" aria-label="User" class="icon icon-user text-primary size-big"></i>
        </template>
      </super-input>
    </section>
  </main>
</template>

<script>
import VideoControls from "./video-controls";
import SuperInput from "./super-input";

export default {
  name: "VideoPreview",
  components: {
    VideoControls,
    SuperInput
  },
  data() {
    return {
      showControls: false
    };
  }
};
</script>

<style lang="scss">
@import "../styles/variables";
#video-settings {
  .video-preview {
    &-wrapper {
      position: relative;
      height: 192px;
    }

    &-user {
      height: 100%;
      min-width: 336px;
      object-fit: cover;
    }
  }
}
</style>
