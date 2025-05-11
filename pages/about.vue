<template>
    <div>
        <h2>About</h2>
        <div>{{ data }}</div>
    </div>
</template>

<script setup>
    // const { data } = await useFetch('api/test?name=mario', {
    //     method: 'POST',
    //     body: {age: 30}
    // })

    const { data } = await useFetch('/api/currency/GBP');

</script>

<style scoped>

</style>