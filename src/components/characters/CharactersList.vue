<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import CharactersCard from './CharactersCard.vue';
export default {
    name: 'Characters List',
    data: () => ({
        characters: []
    }),
    components: {
        CharactersCard
    },
    created() {
        axios.get(endpoint).then(res => {
            this.characters = res.data.docs;
        })
    }
};
</script>

<template>
    <section id="characters" class="my-5">
        <div class="row g-4 row-cols-4">
            <div class="col" v-for="character in characters" :key="character.id">
                <CharactersCard :name="character.name" :image="character.imageUrl" :type="character.type1"
                    :number="character.number" />
            </div>
        </div>
    </section>
</template>