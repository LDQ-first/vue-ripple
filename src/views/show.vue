<template>
    <div class="show">
        <header>
            <h1>Vue Ripple Component</h1>
        </header>
        <article>
            <section>
                <h2>Button Ripple</h2>
                <button @click="showMoal">showModal</button>
            </section>
        </article>
        <footer>
            
        </footer>
        <modal :mdShow="isShowModal" @close="closeModal"></modal>
    </div>
</template>

<script>
    const Ripple = resolve => require(['../components/ripple.vue'], resolve)
    const Modal = resolve => require(['../components/modal.vue'], resolve)

    export default {
        data () {
            return {
                isShowModal: false
            }
        },
        components: {
            Ripple,
            Modal
        },
        methods: {
            showMoal () {
                this.isShowModal = true
            },
            closeModal () {
                this.isShowModal = false
            }
        }
     }
</script>

<style lang="scss" scoped>

</style>