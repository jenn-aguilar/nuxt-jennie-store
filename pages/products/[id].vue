<template>
    <div>
        <Head>
            <Title>Nuxt Jennie Store | {{ product.title }}</Title>
            <Meta name="description" :content="product.description" />
        </Head>
        <ProductDetails :product="product"/>
    </div>
</template>

<script setup>
    const { id } = useRoute().params;
    const uri = "https://fakestoreapi.com/products/" + id;

    // fetch the product
    const { data: product } = await useFetch(uri, {key: id});

    if (!product.value) {
        throw createError({status: 404, statusMessage: 'Product not found',  fatal: true});
    }

    definePageMeta({
        layout: 'products'
    })
</script>

<style lang="scss" scoped>

</style>