<script>
import CharactersList from './characters/CharactersList.vue';
export default {
    name: 'AppMain',
    components: { CharactersList },
    props: {
        characters: Array
    }
}
</script>


<template>
    <main class="container">
        <CharactersList :characters="characters" />
    </main>
</template>

<style></style>