<script setup lang="ts">
import { Authenticator, useAuthenticator } from '@aws-amplify/ui-vue'
import '@aws-amplify/ui-vue/styles.css'
import { Amplify } from 'aws-amplify'
import outputs from '../../amplify_outputs.json'
const auth = useAuthenticator()

Amplify.configure(outputs)
</script>

<template>
  <authenticator v-if="auth.authStatus === 'unauthenticated'" />
</template>
