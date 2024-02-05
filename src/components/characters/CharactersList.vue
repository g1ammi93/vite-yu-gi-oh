<script>
import CharactersCard from './CharactersCard.vue';
export default {
    name: 'Characters List',
    components: { CharactersCard },
    props: {
        characters: Array
    }
};
</script>

<template>
    <section id="characters" class="my-5">
        <div class="row g-4 row-cols-5">
            <div class="col" v-for="character in characters" :key="character.id">
                <CharactersCard :name="character.name" :image="character.imageUrl" :type="character.type1"
                    :number="character.number" />
            </div>
        </div>
    </section>
</template>