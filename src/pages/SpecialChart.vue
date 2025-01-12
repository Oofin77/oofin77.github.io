<script setup lang="ts">
import WeaponChart from '../components/WeaponChart.vue';
import { specialWeapons } from '../data/weapons';
</script>

<template>
    <weapon-chart :weapons="specialWeapons"/>
</template>

<style scoped>

</style>
