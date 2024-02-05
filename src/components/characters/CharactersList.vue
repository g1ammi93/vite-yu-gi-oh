<script>
import { store } from '../../data/store.js';
import CharactersCard from './CharactersCard.vue';
export default {
    name: 'Characters List',
    data: () => ({ store }),
    components: { CharactersCard },
};
</script>

<template>
    <section id="characters" class="my-2">
        <div class="row g-3 row-cols-5">
            <div class="col" v-for="character in store.characters" :key="character.id">
                <CharactersCard :name="character.name" :image="character.imageUrl" :type="character.type1"
                    :number="character.number" />
            </div>
        </div>
    </section>
</template>