<template>
    <div class="home">
        <div class="title">
            langnexus.io
        </div>

        <div class="body">
            <div class="question">
                I would like to learn...
            </div>

            <LangSelect />
        </div>

        <div class="footer">
            Made with ❤️ by Nathan Seymour
        </div>
    </div>
</template>

<script>
    import LangSelect from "../components/LangSelect";
    export default {
        name: 'home',
        components: {LangSelect}
    }
</script>

<style lang="scss" scoped>
    .home {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding: 1em;
        align-items: center;

        .title {
            font-size: 1.5em;
            cursor: pointer;
            width: 100%;
        }

        .body {
            width: 25em;
            margin-bottom: 10em;

            .question {
                margin-bottom: 1em;
            }
        }

        .footer {
            text-align: center;
            width: 100%;
        }
    }
</style>