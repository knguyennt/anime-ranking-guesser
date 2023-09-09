<script setup lang="ts">
import IconCommunity from '../icons/IconCommunity.vue'
name: 'ImageCard'

const props = defineProps<{anime: object}>()
</script>

<template>
    <div>
        <el-card :class="$style.imageCard">
            <div :class="$style.hoverText">
                <h1>{{ props.anime.name }}</h1>
                <p>ranked</p>
                <h2>{{ props.anime.rank }}</h2>
            </div>
            <img :src="props.anime.imageSource" :class="$style.imageBackground" />
        </el-card>
    </div>
</template>

<style module>
.imageCard {
    position: relative;
    text-align: center;

    .hoverText {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        line-height: 10px;

        > h2 {
            color: red;
        }
    }

    .imageBackground {
        opacity: 0.3;
        width: 100%;
    }
}
</style>
