<template>
    <div class="show">
        <header>
            <h1>Vue Ripple Component</h1>
        </header>
        <article>
            <section class="section-btn">
                <div class="ui">
                    <h2>Button Ripple</h2>
                    <ripple class="ripbtn" :isInline="isInline">
                        <button slot="pure" @click="showMoal">showModal</button>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeOne.js}}</code></pre>
                    <pre><code>{{codeOne.html}}</code></pre>
                    <pre><code>{{codeOne.css}}</code></pre>
                </div>
            </section>
            <section class="section-pan">
                <div class="ui">
                    <h2>Panel Ripple</h2>
                    <ripple class="ripbtn" children="one">
                        <div slot="children" class="panel children">
                            <header>
                                <h3>Panel</h3>
                            </header>
                            <div class="content">
                                <p>This is a Panel</p>
                            </div>
                            <button slot="pure" @click="showMoal" class="btn">showModal</button>
                        </div>
                    </ripple>
                </div>
                <div class="code" v-hljs>
                    <pre><code>{{codeTwo.js}}</code></pre>
                    <pre><code>{{codeTwo.html}}</code></pre>
                    <pre><code>{{codeTwo.css}}</code></pre>
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
                isInline: true,
                codeOne: {
                    html: '',
                    css: '',
                    js: ''
                },
                codeTwo: {
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
    data () {
        return {
            isInline: true
        }
    },
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
` 
<!--html-->
<ripple class="ripbtn" :isInline="isInline">
    <button slot="pure" @click="showMoal">showModal</button>
</ripple>
`
                this.codeOne.css = 
`
/*--sass--*/
 .ripbtn {
    margin: 12px;
 }
 `
                this.codeTwo.js =
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
                this.codeTwo.html =
`
<!--html-->
<div class="ui">
    <h2>Panel Ripple</h2>
    <ripple class="ripbtn" children="one">
        <div slot="children" class="panel children">
            <header>
                <h3>Panel</h3>
            </header>
            <div class="content">
                <p>This is a Panel</p>
            </div>
            <button slot="pure" @click="showMoal" class="ripbtn">showModal</button>
        </div>
    </ripple>
</div>
`
                this.codeTwo.css =
`
/*--sass--*/
.section-pan {
    .rippleWrapper {
        width: 80%;
        max-width: 800px;
        margin: 20px auto;
    }
    .panel {
        border: 2px solid #8BE388; 
        padding: 20px;
        background: #EEE;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        header {
        width: 100%;
        text-align: left;
        }
        .btn {
            margin: 10px;
        }
    }
}
`
                
                  
            }

        }
     }
</script>

<style lang="scss" scoped>
    h1,h2,h3,p{
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
    .section-pan {
        .rippleWrapper {
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
        }
        .panel {
            border: 2px solid #8BE388; 
            padding: 20px;
            background: #EEE;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            header {
            width: 100%;
            text-align: left;
            }
            .btn {
                margin: 10px;
            }
        }
    }

</style>