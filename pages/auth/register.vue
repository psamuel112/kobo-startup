<template>
    <div class="">
        <div class="flex ">
            <div class="w-full">
            <testimonial />      
            </div>
            <div class="w-full">
             <registrationForm />
            </div>
        </div>
    </div>
</template>

<script setup>
definePageMeta({
  layout: 'clean',
});
import registrationForm from '~/components/auth/registrationForm.vue';
import testimonial from '~/components/auth/testimonial.vue';
</script>