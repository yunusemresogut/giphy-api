<template>
    <div class="search">
        <input type="text" v-model="query" @keypress.enter="handleSearch"/>
        <button @click="handleSearch">Search</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            query: ''
        }
    },
    methods: {
        handleSearch() {
            this.$emit('SearchRequested', this.query);
        }
    }
}
</script>

<style lang="scss">
    .search input {
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        width: 300px;
    }
    .search button {
        padding: 10px;
        border: 1px solid #000;
        border-radius: 5px;
        width: 100px;
        &:hover {
            background-color: #000;
            color: #fff;
        }
    }
</style>