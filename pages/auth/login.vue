<template>
    <div class="">
        <div class="">
            <loginForm />
        </div>
    </div>
</template>

<script setup>
definePageMeta({
  layout: 'clean',
});
import loginForm from '~/components/auth/loginForm.vue';
</script>