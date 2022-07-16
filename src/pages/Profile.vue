<template>
  <q-header class="bg-white">
    <q-toolbar class="q-pt-xl q-pb-sm">
      <q-btn color="red" flat round dense icon="chevron_left" to="/login" />
      <q-space />
      <q-title class="text-black text-bold">{{ "Profile" }}</q-title>
      <q-space style="margin-right: 34px" />
    </q-toolbar>
    <q-item clickable v-ripple>
      <q-item-section avatar>
        <q-avatar size="xl">
          <img
            src="https://scontent-gig2-1.xx.fbcdn.net/v/t39.30808-6/290750780_5186859131410100_7687568019354966757_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=09cbfe&_nc_eui2=AeGl7NrE45L_IsfS83i19OvrXr-PMX0_KpRev48xfT8qlEAEbDtPhJmUjw7Hjvg6yI2rNaM9R-ZpXdYppM-rxozG&_nc_ohc=1lOa0zRIa3sAX_cZfX8&tn=yu4oiro3Mr-RTGv5&_nc_ht=scontent-gig2-1.xx&oh=00_AT_GKQRTb4TA2w6-sc-HgXzikxfEY8iHEgNKMDAv3OFrrw&oe=62D0F7B4"
          />
        </q-avatar>
      </q-item-section>
      <q-item-section class="text-subtitle2 text-black">
        Luiz Claudio
      </q-item-section>
    </q-item>
  </q-header>
  <q-page>
    <q-dialog
      v-model="dialog"
      maximized
      persistent
      transition-show="slide-left"
      transition-hide="slide-right"
    >
      <card-profile v-if="currItem === 1"></card-profile>
      <card-help v-if="currItem === 2"></card-help>
      <card-settings v-if="currItem === 3"></card-settings>
    </q-dialog>

    <q-item class="content-setting">
      <q-list padding class="text-grey-10" style="width: 100%">
        <q-item
          v-for="i in items"
          :key="i.id"
          clickable
          v-ripple
          @click="openDialog(i)"
        >
          <q-item-section avatar>
            <q-icon :name="i.icon" />
          </q-item-section>
          <q-item-section>{{ i.title }}</q-item-section>
        </q-item>
      </q-list>
    </q-item>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import { ref } from "vue";
import CardSettings from "../components/CardSettings.vue";
import CardHelp from "../components/CardHelp.vue";
import CardProfile from "../components/CardProfile.vue";

export default defineComponent({
  components: {
    CardSettings,
    CardHelp,
    CardProfile,
  },
  name: "profile-page",
  setup() {
    return {
      dialog: ref(false),
      maximizedToggle: ref(true),
      val: ref(false),
      currItem: 0,
      items: [
        {
          id: 0,
          icon: "inbox",
          title: "Inbox",
        },
        {
          id: 1,
          icon: "list",
          title: "Meus dados",
        },
        {
          id: 2,
          icon: "help",
          title: "Ajuda",
        },
        {
          id: 3,
          icon: "settings",
          title: "Settings",
        },
      ],
      openDialog(item) {
        this.currItem = item.id;
        this.dialog = true;
      },
    };
  },
});
</script>

<style lang="scss" scoped></style>
