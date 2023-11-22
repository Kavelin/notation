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
            <div id="editor" >
                <div class="sheet" :style="{gridAutoRows:'24px ' + parts.map(x => x.staves * 150 + 'px').join(' ')}">
                    <div class="measures">
                        <div class="bef-space">
                            Measures
                        </div>
                        <div class="measure-c" :style="{width:('domLength' in measure)?(measure.domLength! + 'px') : '150px'}" :key="i" v-for="(measure, i) in measures">
                            {{ i }}
                        </div>
                    </div>
                    <div class="part" v-for="part in parts" :style="{}">
                        
                        <div class="part-name">
                            {{ part.name }}
                        </div>
                        <div class="staves">
                            <stave v-for="index in part.staves">
                                hey
                            </stave>
                        </div>
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
import stave  from '/components/stave.vue';

interface Measure {
    domLength:number;
    
}

interface Part {
    name: string;
    abrev: string;
    group?: string;
    staves: number;
}

let measures = ref(<Measure[]>[{domLength:200}, {}, {}]);
let parts = ref(<Part[]>[/*{name:"piano", abrev:"pno.", staves:2}, {name:"bass", abrev:"bs", staves:1}, */{name:"drumset", abrev:"ds", staves:1}]);

</script>