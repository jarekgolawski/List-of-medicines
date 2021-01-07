<template>
    <div>
        <form @submit="addMedicine">
            <input type="text" v-model="title" name="title" placeholder="AddMedicine...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name: "AddMedicine",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addMedicine(e) {
            e.preventDefault();
            const newMedicine = {
                id: uuid.v4(),
                title: this.title,
                availability: false
            }
            //Send up to parent
            this.$emit('add-medicine', newMedicine);
            this.title = '';
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>