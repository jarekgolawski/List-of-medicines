<template>
    <div>
        <div v-for="medicine in medicines" v-bind:key = "medicine.id">
            <MedicineItem v-bind:medicine="medicine" v-on:del-medicine="$emit('del-medicine', medicine.id)" />
        </div>
    </div>
</template>

<script>
import MedicineItem from './MedicineItem.vue'

export default {
    name: "Medicines",
    components: {
        MedicineItem
    },
    props: ["medicines"]
}
</script>

<style scoped>

</style>