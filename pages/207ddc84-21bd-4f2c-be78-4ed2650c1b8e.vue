<template>
    <div class="size-full">
        <TresCanvas v-bind="gl">
            <!--TresPerspectiveCamera :position="[0, 0, 15]"></TresPerspectiveCamera-->
            <!--TresDirectionalLight :position="[0, 0, 1]"></TresDirectionalLight-->
            <Sky :elevation="1" :azimuth="185"></Sky>
            <Suspense>
                <Ocean></Ocean>
            </Suspense>
            <TresMesh :position-y="1">
                <TresBoxGeometry :args="[1, 1, 1]"></TresBoxGeometry>
                <Grid :args="[10.5, 10.5]" cell-color="#82dbc5" :cell-size="0.6" :cell-thickness="0.5"
                section-color="#fbb03b" :section-size="2" :section-thickness="1.3" :infinite-grid="true" :fade-from="0"
                :fade-distance="12" :fade-strength="1"></Grid>
            </TresMesh>
            <MapControls></MapControls>
        </TresCanvas>
    </div>
</template>

<script setup>
import { Ocean, MapControls, Sky, Grid } from "@tresjs/cientos";
import { TresCanvas } from "@tresjs/core";
import { ACESFilmicToneMapping, SRGBColorSpace, NoToneMapping } from "three";

/*const gl = {
    clearColor: '#333',
    outputColorSpace: SRGBColorSpace,
    toneMapping: ACESFilmicToneMapping,
    toneMappingExposure: 1,
}*/

const gl = {
    clearColor: '#333',
    alpha: true,
    outputColorSpace: SRGBColorSpace,
    toneMapping: NoToneMapping,
}
</script>