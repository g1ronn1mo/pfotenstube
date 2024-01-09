<script setup lang="ts">
// Import predefined theme
import { ThemeSupa } from '@supabase/auth-ui-shared'
import { Auth } from '@nuxtbase/auth-ui-vue'
import { createClient } from '@supabase/supabase-js'

const supabaseClient = useSupabaseClient()
const themeColor = useColorMode()
</script>

<template>
  <Auth
    :supabase-client="supabaseClient"

    :providers="['google']"
    :appearance="{
      theme: ThemeSupa,
    }"
    :theme="themeColor.value"
  />
</template>
