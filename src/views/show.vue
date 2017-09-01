<template>
    <div class="show">
        <header>
            <h1>Vue Ripple Component</h1>
        </header>
        <article>
            <section>
                <div class="ui">
                    <h2>Button Ripple</h2>
                    <ripple class="ripbtn">
                        <button slot="pure" @click="showMoal">showModal</button>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeOne.js}}</code></pre>
                    <pre><code>{{codeOne.html}}</code></pre>
                    <pre><code>{{codeOne.css}}</code></pre>
                </div>
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
                modalMessage: 'This is a Modal',
                codeOne: {
                    html: '',
                    css: '',
                    js: ''
                }
            }
        },
        components: {
            Ripple,
            Modal
        },
        created () {
            this.setCode()
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
            },
            setCode () {
                this.codeOne.js =
`
/*-- js --*/
const Ripple = resolve => require(['../components/ripple.vue'], resolve)
export default { 
    components: {
        Ripple
    },
    methods: {
        showMoal () {
            this.isShowModal = true
        }
    }
}
`
                this.codeOne.html = 
` <!--html-->
<ripple class="ripbtn">
    <button slot="pure" @click="showMoal">showModal</button>
</ripple>
`
                this.codeOne.css = 
`
/*--css--*/
 .ripbtn {
    margin: 12px;
 }
 `
                
                  
            }

        }
     }
</script>

<style lang="scss" scoped>
    h1,h2 {
        margin: 10px 0;
    }
    .ripbtn {
        margin: 12px;
    }
    .code {
        width: 80%;
        max-width: 768px;
        margin: 0 auto;
    }
</style>