<template>
  <div class="control mb-8 row">
    <label
      class="flex-1 size-normal text-grey-90"
      :for="settingItem.id"
      :id="settingItem.labelId"
    >{{settingItem.labelText}}</label>
    <super-dropdown
      :id="settingItem.dropdownId"
      :name="settingItemName"
      :aria-labelledby="settingItem.labelId"
    >
      <option
        class="super-option"
        v-for="option in settingItem.options"
        :key="option.id"
        :value="option.text"
      >{{option.text}}</option>
    </super-dropdown>
  </div>
</template>

<script>
import SuperDropdown from "./super-dropdown";

export default {
  name: "SettingControlItem",
  components: {
    SuperDropdown
  },
  props: {
    settingItem: {
      type: Object,
      required: true
    }
  },
  computed: {
    settingItemName() {
      if (this.settingItem) {
        return (
          this.settingItem.id.charAt(0).toUpperCase() +
          this.settingItem.id.slice(1)
        );
      }
    }
  }
};
</script>
