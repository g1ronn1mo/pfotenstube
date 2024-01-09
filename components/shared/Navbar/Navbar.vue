<script setup>
export interface NavItem {
  name: string
  icon: string
  path: string
}

export interface NavbarItems {
  navItems: NavItem[]
  menuItems: NavItem[]
}

const { navItems, menuItems } = defineProps<NavbarItems>()

const { mdAndUp } = useDisplay()

const tempDrawer = ref(true)
</script>

<template>
  <v-app-bar app>
    <!-- The Icon on the left to open and close the drawer -->
    <v-app-bar-nav-icon
      class="hidden-lg-and-up"
      @click="tempDrawer = !tempDrawer"
    />
    <v-spacer />
    <nuxt-link to="/" class="d-flex align-items-center">
      <img src="/logo.png" alt="Logo" height="80" width="80">
    </nuxt-link>
    <v-spacer />
    <!-- Icons on the right side -->
    <!-- Settings Menu -->

    <v-menu
      transition="scale-transition"
    >
      <template #activator="{ props }">
        <v-btn
          color="primary"
          v-bind="props"
        >
          <v-icon> mdi-dots-vertical </v-icon>
        </v-btn>
      </template>

      <v-list>
        <v-list-item v-for="routeItem in menuItems" :key="routeItem.name">
          <nuxt-link :to="routeItem.path" class="text-decoration-none">
            <v-icon>{{ routeItem.icon }}</v-icon>
            {{ routeItem.name }}
          </nuxt-link>
        </v-list-item>
        <v-list-item>
          <Logout />
        </v-list-item>
      </v-list>
    </v-menu>
  </v-app-bar>

  <!-- Add a navigation drawer on the left side on small screens -->
  <v-navigation-drawer
    v-model="tempDrawer"
    :permanent="mdAndUp.value"

    app
  >
    <!-- Navigation links on medium to small -->
    <v-list
      :lines="false"
      density="compact"
      nav
    >
      <v-list-item v-for="routeItem in navItems" :key="routeItem.name">
        <nuxt-link :to="routeItem.path" class="text-decoration-none">
          <v-icon>{{ routeItem.icon }}</v-icon>
          {{ routeItem.name }}
        </nuxt-link>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>
