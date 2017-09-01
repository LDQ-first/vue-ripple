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
        <modal :mdShow="isShowModal" @close="closeModal">
            <p slot="message">
                {{modalMessage}}
            </p>
            <div slot="btnGroup" class="btnGroup">
                <button class="md-close" @click="closeModal">closeModal</button>
            </div>
        </modal>
    </div>
</template>

<script>
    const Ripple = resolve => require(['../components/ripple.vue'], resolve)
    const Modal = resolve => require(['../components/modal.vue'], resolve)

    export default {
        data () {
            return {
                isShowModal: false,
                modalMessage: 'This is a Modal'
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
            },
            setModalMessage (str) {
                this.modalMessage = str
            }
        }
     }
</script>

<style lang="scss" scoped>

</style>