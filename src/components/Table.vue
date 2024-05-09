<script setup>
    import Line from './Line.vue';
    const props = defineProps(["pessoas"]);
</script>

<template>
    <table>
        <thead>
            <th>Nome</th>
            <th>CPF</th>
            <th>E-mail</th>
        </thead>
        <tbody>
            <Line v-for="pessoa in pessoas"
            :pessoa="pessoa"
            />
        </tbody>
    </table>
</template>