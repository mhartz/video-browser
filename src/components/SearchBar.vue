<template>
    <div>
        <input @input="onInput" />
    </div>
</template>


<script>
/* eslint-disable */

export default {
    name: 'SearchBar',
    methods: {
        onInput(event) {
            this.$emit('termChange', event.target.value);
        }
    }
}
</script>

<style>

</style>
