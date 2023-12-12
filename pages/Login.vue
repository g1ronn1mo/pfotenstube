<script setup lang="ts">
// Import predefined theme
import { ThemeSupa } from '@supabase/auth-ui-shared'
import { Auth } from '@nuxtbase/auth-ui-vue'
import { createClient } from '@supabase/supabase-js'

const supabaseClient = useSupabaseClient()
</script>

<template>
  <Auth
    :supabase-client="supabaseClient"
    :appearance="{
      theme: ThemeSupa,
    }"
  />
</template>
