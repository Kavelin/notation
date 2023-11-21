<template>
    <div id="container">
        <div id="top-bar">
            <h1>:)</h1>
        </div>
        <div id="not-top-bar">
            <div id="palette">
                <h3>Palette</h3>
                <div>
                    
                </div>
            </div>
            <div id="editor">
                <div class="sheet">
                    <div class="measures">
                        Measures
                        <div class="measure-c" :key="i" v-for="(measure, i) in measures">
                            {{ i }}
                        </div>
                    </div>
                    <div class="part" v-for="part in parts">
                        
                    </div>
                </div>
            </div>
            <div id="modify">
                <h3>Modify</h3>
                <div>
                    
                </div>
            </div>
        </div>
    </div>
</template>
<script setup lang="ts">

let measures = ref(Array(10));
let parts = ref(Array(3));
</script>