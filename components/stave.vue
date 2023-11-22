<template>
    <div class="stave" ref="el"></div>
</template>
<script setup lang="ts">
import Vex from 'vexflow';
const el = ref(null);
onMounted(() => {
    const { Renderer, Stave } = Vex.Flow;
    const renderer = new Renderer(el.value!, Renderer.Backends.SVG);
    renderer.resize(500, 120);
    const context = renderer.getContext();
    context.setFont('Arial', 10);
    const stave = new Stave(0, 0, 400);
    stave.addClef('treble').addTimeSignature('4/4');
    stave.setContext(context).draw();
});
</script>