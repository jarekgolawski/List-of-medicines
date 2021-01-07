<template>
    <div class="medicine-item" v-bind:class="{'is-available':medicine.availability}">
        <p>
            <input type="checkbox" v-on:change="markAvailable">
            {{medicine.title}}
            <button @click="$emit('del-medicine', medicine.id)"
            class="del">x</button></p>
    </div>
</template>

<script>
export default {
    name: "MedicineItem",
    props: ["medicine"],
    methods: {
        markAvailable() {
           this.medicine.availability = !this.medicine.availability;
        }
    }
}
</script>

<style scoped>
    .medicine-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-available {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>