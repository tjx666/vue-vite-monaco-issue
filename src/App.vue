<script setup lang="ts">
import { ref } from 'vue';
import MonacoEditor from './components/monacoEditor/MonacoEditor.vue';

const source = ref(
    JSON.stringify(
        {
            name: 'ly',
            age: 18,
            alone: true,
        },
        null,
        4,
    ),
);

setTimeout(() => {
    source.value = JSON.stringify({
        name: 'xxx',
    });
}, 3000);

</script>

<template>
    <MonacoEditor language="json" :source="source" />
</template>

<style lang="scss">
@import './normalize.css';

html,
body,
#app {
    width: 100vw;
    height: 100vh;
}

#app {
    .editor {
        width: 100%;
        height: 100%;
    }
}
</style>
