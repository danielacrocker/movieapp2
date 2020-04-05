<template>
  <nav>
    <v-toolbar>
      <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Ninja</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text ><span>Sign Out</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
      <v-overflow-btn
        :items="dropdown_font"
        label="Select font"
        hide-details
        class="pa-0"
      ></v-overflow-btn>

      <template v-if="$vuetify.breakpoint.mdAndUp">
        <v-divider vertical></v-divider>

        <v-overflow-btn
          :items="dropdown_edit"
          editable
          label="Select size"
          hide-details
          class="pa-0"
          overflow
        ></v-overflow-btn>

        <v-divider vertical></v-divider>

        <v-spacer></v-spacer>

        <v-btn-toggle
          v-model="toggle_multiple"
          color="primary"
          dense
          group
          multiple
        >
          <v-btn :value="1" text>
            <v-icon>mdi-format-bold</v-icon>
          </v-btn>

          <v-btn :value="2" text>
            <v-icon>mdi-format-italic</v-icon>
          </v-btn>

          <v-btn :value="3" text>
            <v-icon>mdi-format-underline</v-icon>
          </v-btn>

          <v-btn :value="4" text>
            <v-icon>mdi-format-color-fill</v-icon>
          </v-btn>
        </v-btn-toggle>

        <div class="mx-4"></div>

        <v-btn-toggle
          v-model="toggle_exclusive"
          color="primary"
          dense
          group
        >
          <v-btn :value="1" text>
            <v-icon>mdi-format-align-left</v-icon>
          </v-btn>

          <v-btn :value="2" text>
            <v-icon>mdi-format-align-center</v-icon>
          </v-btn>

          <v-btn :value="3" text>
            <v-icon>mdi-format-align-right</v-icon>
          </v-btn>

          <v-btn :value="4" text>
            <v-icon>mdi-format-align-justify</v-icon>
          </v-btn>
        </v-btn-toggle>
      </template>
    </v-toolbar>

    <v-navigation-drawer v-model="drawer" app class="primary">
      <v-list>
        <v-list-item  v-for="link in links" :key="link.icon" router :to="link.route">
          <v-list-item-action>
            <v-icon class="white--text">
              {{ link.icon }}
            </v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="white--text">
              {{ link.text }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data: () =>{
    return {
      dropdown_font: [],
      toggle_exclusive: [],
      toggle_multiple: [],
      dropdown_edit: [],
      drawer: false,
      links: [
        { icon: 'dashboard', text: 'Dashboard', route: '/'},
        { icon: 'folder', text: 'My Projects', route: '/projects'},
        { icon: 'person', text: 'Team', route: '/team'}
      ]
    };
  },
  methods: {},
  props: {
    // items: String,
  }
}
</script>

<style scoped>
  
</style>