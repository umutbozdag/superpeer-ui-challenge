<template>
  <section class="setting-controls mt-24">
    <form @submit.prevent>
      <setting-control-item
        v-for="settingItem in settingControlItems"
        :setting-item="settingItem"
        :key="settingItem.id"
      />

      <div class="control row mb-24">
        <label class="flex-1 size-normal play-sound-label text-grey-90">Sound Test</label>

        <super-button
          @clicked="playSound"
          aria-label="Play test sound"
          outlined
          variant="primary"
          class="play-sound-btn flex-2"
        >
          <span>Play Sound</span>
        </super-button>
      </div>
    </form>
  </section>
</template>

<script>
import SuperButton from "./super-button";
import SettingControlItem from "./setting-control-item";

export default {
  name: "SettingControls",
  components: {
    SuperButton,
    SettingControlItem
  },
  data() {
    return {
      testSoundSrc:
        "http://codeskulptor-demos.commondatastorage.googleapis.com/descent/gotitem.mp3",
      settingControlItems: [
        {
          id: "cameras",
          labelText: "Camera",
          options: [
            {
              id: 0,
              text: "Facetime HD Camera"
            },
            {
              id: 1,
              text: "Facetime HD Camera"
            }
          ],
          dropdownId: "cameras",
          labelId: "camera"
        },
        {
          id: "speakers",
          labelText: "Speaker",
          options: [
            {
              id: 0,
              text: "Built-in Output (Headp..."
            },
            {
              id: 1,
              text: "Built-in Output (Headp..."
            }
          ],
          dropdownId: "speakers",
          labelId: "speaker"
        },
        {
          id: "microphones",
          labelText: "Microphone",
          options: [
            {
              id: 0,
              text: "Built-in Microphone (E..."
            },
            {
              id: 1,
              text: "Built-in Microphone (E..."
            }
          ],
          dropdownId: "microphones",
          labelId: "microphone"
        }
      ]
    };
  },
  methods: {
    playSound() {
      const audio = document.createElement("audio");
      audio.style.display = "none";
      audio.src = this.testSoundSrc;
      audio.play();
    }
  }
};
</script>

<style lang="scss" scoped>
.play-sound-label {
  margin-right: -11px;
}
</style>




