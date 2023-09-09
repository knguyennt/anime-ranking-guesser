<script setup lang="ts">
import NavBar from '../components/common/NavBar.vue'
import ImageCard from '../components/common/ImageCard.vue'
import _ from 'lodash';
import { onMounted, reactive, watch } from 'vue';

declare interface Anime {
    imageSource: String;
    name: String;
    rank: Number;
}

const animes = [
    {
        imageSource: 'https://venturology.files.wordpress.com/2017/01/2-1024x631.jpg',
        name: 'Kimi no nawa',
        rank: 10
    },
    {
        imageSource: 'https://sm.ign.com/t/ign_ap/screenshot/default/fullmetal-f_9aj1.1200.jpg',
        name: 'Fullmetal Alchemist',
        rank: 1
    },
    {
        imageSource: 'https://media.thenerdstash.com/wp-content/uploads/2022/06/kaguya-sama-love-is-war-cover-image.jpg',
        name: 'Kaguya: Love is war',
        rank: 3
    },
    {
        imageSource: 'https://img-cdn.2game.vn/pictures/images/2016/3/3/001.png',
        name: 'Zetsuen no Tempest',
        rank: 28
    },
    {
        imageSource: 'https://upload.wikimedia.org/wikipedia/en/8/85/Guilty_Crown_Main_Characters.jpg',
        name: 'Guilty Crown',
        rank: 8
    }
]

const state = reactive({
    guessAnime: {} as Anime,
    displayAnime: {} as Anime,
    isWinner: false,
})

const getAnime = () => {
    const randomAnime = _.shuffle(animes)

    _.isEmpty(state.displayAnime) ? state.displayAnime = randomAnime[0] : state.displayAnime = {...state.guessAnime}

    do {
        state.guessAnime = _.sample(animes) as Anime
    }
    while (_.isEqual(state.guessAnime, state.displayAnime))
}

const checkIfSelectCorrect = (guess : String) => {
    const answer = state.guessAnime.rank < state.displayAnime.rank ? 'Lower' : 'Higher'
    state.isWinner = answer === guess

    if (state.isWinner) {
        getAnime()
    }
}

onMounted(() => {
    getAnime()
})
</script>

<template>
    <main>
        <NavBar />
        <div :class="$style.mainSection">
            <ImageCard :anime="state.displayAnime" :hideRank="false" @answer="checkIfSelectCorrect"/>
            <ImageCard :anime="state.guessAnime" :hideRank="true" @answer="checkIfSelectCorrect"/>
        </div>
    </main>
</template>

<style module>
.mainSection {
    display: flex;
}
</style>
