<template>
    <div id="app">
        <router-view/>
    </div>
</template>

<style lang="scss">
    @import url('https://fonts.googleapis.com/css?family=Kulim+Park&display=swap');

    html, body, #app {
        width: 100%;
        height: 100%;
        overflow: hidden;
        background: rgba(235,235,230,1);
    }

    * {
        box-sizing: border-box;
        padding: 0;
        margin: 0;
        font-family: 'Kulim Park', sans-serif;
    }
</style>
