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
    <div class="my-card character-card text-center p-1 rounded-3 d-flex flex-column align-items-center justify-content-center"
        :class="{
            'bg-grass': type === 'Grass',
            'bg-fire': type === 'Fire',
            'bg-water': type === 'Water'
        }">
        <div class="img-container rounded-circle">
            <img :src="image" :alt="name" class="img-fluid rounded-circle mb-1">
        </div>
        <div> {{ number }}</div>
        <h4> {{ name }}</h4>

        <div class="fst-italic"> {{ type }}</div>
    </div>
</template>

<style scoped>
.my-card {
    width: 220px;
    height: 220px;
    margin: auto;
}

.img-container {
    max-height: 100px;
    width: 120px;
}


img {
    width: 120px;
    max-height: 100px;
    cursor: pointer;
}

.bg-fire {
    background-color: rgb(253, 223, 223);
}

.bg-water {
    background-color: rgb(222, 243, 253);
}

.bg-grass {
    background-color: rgb(222, 253, 224);
}
</style>