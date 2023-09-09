<script setup lang="ts">
import IconCommunity from '../icons/IconCommunity.vue'
name: 'NavBar'
</script>

<template>
    <div>
        <el-menu mode="horizontal" :ellipsis="false" :class="$style.topNav">
            <el-menu-item>
                <el-icon :size="18">
                    <IconCommunity/>
                </el-icon>
                <span>Home</span>
            </el-menu-item>
            <p :class="$style.title">Anime Ranking Guesser</p>
        </el-menu>
    </div>
</template>

<style module>
.topNav {
    background-color: #9400FF;

    .title {
        flex-grow: 3;
        text-align: center;
        font-size: 20px;
        color: white;
    }
}
</style>