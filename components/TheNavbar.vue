<script setup>
import Navbar from './shared/Navbar.vue'

const navItems = [
  { name: 'Home', icon: 'mdi-home', path: '/' },
//   { name: 'Workflows', icon: 'mdi-sitemap', path: '/workflows' },
//   { name: 'Testing', icon: 'mdi-account-question', path: '/testing' },
//   { name: 'Data', icon: 'mdi-folder', path: '/data' },
//   { name: 'Add Project', icon: 'mdi-plus-box', path: '/projects' },
]

const menuItems = [
  { name: 'Settings', icon: 'mdi-account-cog', path: '/settings' },
  { name: 'Information', icon: 'mdi-information', path: '/Information' },
]
</script>

<template>
  <Navbar />
</template>
