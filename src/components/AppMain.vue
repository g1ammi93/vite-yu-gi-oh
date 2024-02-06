<script>
import CharactersList from './characters/CharactersList.vue';
export default {
    name: 'AppMain',
    components: { CharactersList },
};
</script>


<template>
    <main class="container">
        <div class="interior-container rounded-4">
            <CharactersList />
        </div>
    </main>
</template>

<style scoped>
img {
    width: 80px;
    max-height: 80px;
    cursor: pointer;
    margin-top: 30px;
}

.interior-container {
    height: 470px;
    margin-top: 20px;
    background-color: rgb(98, 102, 107);
    border: 50px solid rgb(222, 222, 222);
    border-width: 50px 30px 50px 30px;
    box-sizing: content-box;
    overflow-y: scroll;
    overflow-x: hidden;
    padding: 15px;
}
</style>