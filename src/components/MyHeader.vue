<script setup lang="ts">
import DarkMode from '@/components/DarkMode.vue'
import Button from '@/volt/Button.vue'
import { Amplify } from 'aws-amplify'
import { useAuthenticator } from '@aws-amplify/ui-vue'
import outputs from '../../amplify_outputs.json'
Amplify.configure(outputs)

const auth = useAuthenticator()
</script>

<template>
  <div class="relative sticky inset-x-0 top-0 m-2 h-12 flex justify-end gap-5 items-center">
    <Button class="h-6" v-if="auth.authStatus === 'authenticated'" @click="auth.signOut">
      Sign Out</Button
    >
    <DarkMode />
  </div>
</template>
