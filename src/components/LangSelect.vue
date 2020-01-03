<template>
    <div class="langselect">
        <div @click="toggle()" class="body">
            <div class="text"> {{ text }} </div>
            <div class="carrot">&or;</div>
        </div>

        <div :class="['expander', expanded ? 'expanded' : '']">
            <div @click="nav(item)" v-for="item of items" class="item">
                {{ item.title }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "LangSelect",
        props: {
            items: {
                type: Array,
                default() {
                    return [
                        {
                            title: 'German',
                            link: 'https://de.langnexus.io'
                        },
                        {
                            title: 'The Source Code',
                            link: 'https://github.com/teach-languages'
                        }
                    ];
                }
            }
        },
        data() {
            return {
                text: 'Click Here...',
                expanded: false
            };
        },
        methods: {
            toggle() {
                this.expanded = !this.expanded;
            },
            nav(item) {
                this.expanded = false;
                this.text = item.title;
                window.location.href = item.link;
            }
        },
        mounted() {
            const pos = [
                'Languages are for Everyone.',
                'Open Source Learning.',
                'Broaden your Horizons.',
                'For the Love of Languages.'
            ];
            const num = Math.floor(Math.random() * pos.length);
            this.text = pos[num];
        }
    }
</script>

<style lang="scss" scoped>
    .langselect {
        user-select: none;
        position: relative;
        background: rgba(245,245,246,1);

        transition: 500ms;
        box-shadow: 2px 2px 10px 1px rgba(0,0,0,0.2);

        &:hover {
            box-shadow: 2px 2px 10px 1px rgba(0,0,0,0.1);
        }

        .body {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            cursor: pointer;
            border: 1px solid black;
            padding: 1em;
            z-index: 1000;
            position: relative;

            .carrot {
                font-weight: 800;
            }
        }

        .expander {
            position: absolute;
            top: 100%;
            right: 0;
            left: 0;
            height: 0;
            opacity: 0.75;
            transition: 300ms ease-in;
            overflow: hidden;
            background: transparent;
            text-overflow: clip;
            z-index: 1;

            &.expanded {
                opacity: 1;
                height: 200%;
            }

            .item {
                padding: 1em;
                text-overflow: clip;
                transition: 300ms;
                cursor: pointer;
                background: rgba(240,240,241,1);
                z-index: 2;

                &:hover {
                    filter: brightness(0.98);
                }
            }
        }
    }
</style>