<script>
import CharactersList from './characters/CharactersList.vue';
export default {
    name: 'AppMain',
    components: { CharactersList },
};
</script>


<template>
    <main class="container">
        <div class="interior-container rounded-3">
            <CharactersList />
        </div>

    </main>
</template>

<style>
.exterior-container {
    width: 100%;
    height: 600px;
}

.interior-container {
    height: 500px;
    margin-top: 150px;
    background-color: gray;
}
</style>