<template>
<div id="app">
    <app-view/>
</div>
</template>

<script>
import AppView from './AppView.vue'

export default {
    components: {
        AppView
    },
    head: {
        titleTemplate (title) {
            if (title) return `${title}`
            return ''
        },
        htmlAttrs: {
            lang: 'zh'
        },
        meta: [
            { charset: 'utf-8' },
            { name: 'viewport', content: 'width=device-width, initial-scale=1' }
        ]
    }
}
</script>

<style>
#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}
</style>
