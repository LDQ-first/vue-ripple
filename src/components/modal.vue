<template>
    <div class="modal" v-show="mdShow">
        <div class="md-content">
            <header>
                <h3 class="">Modal</h3>
                
            </header>
            <article>
                <p>This is a Modal</p>
            </article>
            <footer>
                <button class="md-close" @click="closeModal">closeModal</button>
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

</style>