<script>

export default {
    name: 'Characters Card',
    props: {
        name: String,
        image: String,
        type: String,
        number: Number
    }
}
</script>

<template>
    <div class="character-card text-center p-2">
        <img :src="image" :alt="name" class="img-fluid rounded-circle mb-3">
        <div> {{ number }}</div>
        <h4> {{ name }}</h4>

        <div> {{ type }}</div>
    </div>
</template>