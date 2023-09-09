<script setup lang="ts">
import NavBar from '../components/common/NavBar.vue'
import ImageCard from '../components/common/ImageCard.vue'

const anime = {
    imageSource: 'https://images3.alphacoders.com/132/1322308.jpeg',
    name: 'Kimi no nawa',
    rank: 10
}
</script>

<template>
    <main>
        <NavBar />
        <div :class="$style.mainSection">
            <ImageCard :anime="anime" :hideRank="true"/>
            <ImageCard :anime="anime"/>
        </div>
    </main>
</template>

<style module>
.mainSection {
    display: flex;
}
</style>
