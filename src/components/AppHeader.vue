<script>
export default {
    name: 'AppHeader',
    data: () => ({
        searchTerm: '',
        types: [
            "Bug",
            "Dark",
            "Dragon",
            "Electric",
            "Fairy",
            "Fighting",
            "Fire",
            "Flying",
            "Ghost",
            "Grass",
            "Ground",
            "Ice",
            "Normal",
            "Poison",
            "Psychic",
            "Rock",
            "Steel",
            "Water"
        ]
    }),
    methods: {
        selectType(type) {
            if (type === "All") {
                this.$emit('type-selected', '');
            } else {
                this.$emit('type-selected', type);
            }
        }
    }
};
</script>


<template>
    <header class="container d-flex justify-content-between">
        <!-- Inerisco l'immagine -->
        <img src="../assets/img/Poké_Ball_icon.svg.png" alt="">
        <!-- Creo il bottone per Filtrare i Pokemon -->
        <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenu2" data-bs-toggle="dropdown"
                aria-expanded="false">
                Seleziona il tipo
            </button>
            <ul class="dropdown-menu">
                <li @click="selectType('All')">
                    <button class="dropdown-item" type="button">All</button>
                </li>
                <li v-for="type in types" :key="type" @click="selectType(type)">
                    <button class="dropdown-item" type="button">{{ type }}</button>
                </li>
            </ul>
        </div>

    </header>
</template>

<style scoped>
img {
    width: 80px;
    max-height: 80px;
    cursor: pointer;
    margin-top: 30px;
}

.dropdown {
    margin-top: 50px;
}
</style>