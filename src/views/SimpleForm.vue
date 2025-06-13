<script setup>
import BaseInput from '@/components/BaseInput.vue';
import { ref } from 'vue';
</script>

<template>
    <BaseInput
        label="Name"
        v-model="data.nombre"
        type="password"
    />
    <BaseInput
        label="Name"
        v-model="data.nombre"
        type="text"
    />
</template>

<script>
    const data = ref({
        nombre: "",
        email: ""
    })
</script>