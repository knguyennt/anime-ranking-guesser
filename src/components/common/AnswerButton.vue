<script setup lang="ts">
import { computed, reactive } from 'vue';
import IconCommunity from '../icons/IconCommunity.vue'
name: 'AnswerButton'


const props = defineProps<{ higher: boolean }>()
const emit = defineEmits(['select'])

const state = reactive({
    text: computed(() => props.higher ? 'Higher' : 'Lower')
})
</script>

<template>
    <div>
        <el-button type="primary" @click="emit('select', state.text)">{{ state.text }}</el-button>
    </div>
</template>

<style module>
</style>