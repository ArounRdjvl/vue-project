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
  <div
    class="sticky inset-x-0 top-0 m-2 h-15 grid justify-stretch items-center"
    :class="
      auth.authStatus === 'authenticated'
        ? 'md:grid-cols-[12rem_auto_12rem] grid-cols-[1rem_auto_12rem]'
        : 'grid-cols-[4rem_auto_4rem]'
    "
  >
    <div></div>
    <h4 class="underline decoration-double place-self-center shrink-0">Demo Project</h4>
    <div class="flex items-center gap-5">
      <Button class="h-6" v-if="auth.authStatus === 'authenticated'" @click="auth.signOut">
        Sign Out
      </Button>
      <DarkMode />
    </div>
  </div>
</template>
