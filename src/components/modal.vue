<template>
    <div class="modal" v-show="mdShow">
        <div class="md-content">
            <header>
                <h3 class="">Modal</h3>
                <span class="close" @click="closeModal"></span>
            </header>
            <article>
                <slot name="message"></slot>
            </article>
            <footer>
                <slot name="btnGroup"></slot>
            </footer>
        </div>
        <div class="md-overlay " v-show="mdShow" @click="closeModal"></div>
    </div>
</template>

<script>
    export default {
        props: ['mdShow'],
        data () {
            return {

            }
        },
        methods: {
            closeModal () {
                this.$emit('close')
            }
        }
    }
</script>

<style lang="scss" scope>
    .modal {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        .md-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.3);
            z-index: 10;
            cursor: pointer;
        }
    }
    .md-content {
        position: absolute;
        z-index: 20;
        padding: 20px;
        background: rgba(255, 255, 255, 0.8);
        box-shadow: 0 19px 60px rgba(0,0,0,.298039),
                    0 15px 20px rgba(0,0,0,.219608);
        width: 75%;
        max-width: 768px;
        animation: move 0.8s ease-in-out;
        &:hover {
            background: rgba(255, 255, 255, 1);
        }
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 10px 0;
            h3 {
                margin: 0;
            }
        }
        article {
            text-align: left;
            margin: 10px 0;
        }
        footer {
            margin: 10px 0;
        }
    }
    @keyframes move {
        0% {
            opacity: 0;
            transform: translateY(50%);
        }
        100% {
            opacity: 1;
            transform: translateY(0%);
        }
    }
    .close {
        display: inline-block;
        cursor: pointer;
        transition: all .8s ease-in-out;
        position: relative;
        width: 2em;
        height: 2em;
        &::after,&::before {
            content: "";
            display: inline-block;
            width: 5px;
            height: 2rem;
            position: absolute;
            top: 50%;
            left: 50%;
            margin-left: -2.5px;
            margin-top: -1em;
            background: #fff;
            transition: all .8s ease-in-out;
            border-radius: 10px;
            box-shadow: 0 0 3px 0 rgba(0,0,0,.3)
        }
        &::before {
            transform: rotate(45deg)
        }
        &::after {
            transform: rotate(-45deg)
        }
        &:hover::after,&:hover::before {
            background: #ee5715;
            box-shadow: 0 0 6px 0 rgba(0,0,0,.4)
        }

        &:hover::before {
            transform: rotate(405deg)
        }

        &:hover::after {
            transform: rotate(315deg)
        }

    }
</style>