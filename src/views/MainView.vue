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
        <ImageCard :anime="anime"/>
    </main>
</template>
