<template>
        <el-container class="h-full">
            <el-aside>Aside</el-aside>
            <el-container>
                <el-header>Header</el-header>
                <el-main><RouterView></RouterView></el-main>
                <el-footer>Footer</el-footer>
            </el-container>
        </el-container>
</template>

<script setup>
import { getCurrentInstance } from "vue";
import ElementPlus from "element-plus";
import Tres from "@tresjs/core";

const { appContext: { app } } = getCurrentInstance();
app.use(ElementPlus);
app.use(Tres);
</script>

<style>
@import "./node_modules/element-plus/dist/index.css";

html, body, #app {
    height: 100%;
}
</style>