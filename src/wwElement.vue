<template>
  <Avatar :label="avatarLabel" class="mr-2" size="xlarge" />
</template>

<script>
import Avatar from 'primevue/avatar'
import Primevue from 'primevue/config'
import "primevue/resources/themes/lara-light-indigo/theme.css";

export default {
  beforeCreate: function () {
    this.$.appContext.app.use(Primevue)
    this.$.appContext.app.component('Avatar', Avatar)
  },
  props: {
    content: { type: Object, required: true },
  },
  computed: {
    avatarLabel() {
      return this.content.avatarText.length ? this.content.avatarText.substring(0, 1) : ""
    }
  },
};
</script>
